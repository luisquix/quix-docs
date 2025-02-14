# Process - threshold detection

In this part of the tour you'll learn how to create a transform. The transform detects if CPU load exceeds a certain threshold, and if so, sends a dataframe to its output topic.

## Watch the video

<div style="position: relative; padding-bottom: 61.93103448275862%; height: 0;"><iframe src="https://www.loom.com/embed/32f38336c4344d23baab978f421f78c9?sid=6365be3a-abaa-4e06-8b26-c3652c8d612e" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen style="position: absolute; top: 0; left: 0; width: 100%; height: 100%;"></iframe></div>

## Create the transform

To create the threshold detection transform:

1. In your `Develop` environment, click on `Code Samples` in the main left-hand navigation. 
2. Select the `Python`, `Transformation`, and `Basic templates` filters.
3. For `Starter transformation` click `Preview code`.
4. Click `Edit code`.
5. Name the transform "CPU Threshold".
6. Select the input topic `cpu-load`.
7. For the output topic, add a new topic called `cpu-spike`.
8. Click `Save as Application`.
9. In the project view click on `main.py` to edit it.
10. Replace all the code in `main.py` with the following:

    ```python
    import quixstreams as qx
    import os
    import pandas as pd

    client = qx.QuixStreamingClient()

    topic_consumer = client.get_topic_consumer(os.environ["input"], consumer_group = "empty-transformation")
    topic_producer = client.get_topic_producer(os.environ["output"])

    def on_dataframe_received_handler(stream_consumer: qx.StreamConsumer, df: pd.DataFrame):
        cpu_load = df['CPU_Load'][0]
        
        print(f"CPU Load: {cpu_load} %")    
        stream_producer = topic_producer.get_or_create_stream(stream_id = stream_consumer.stream_id)
        if cpu_load > 50: # hard-coded threshold
            print(f"CPU spike of {cpu_load} detected!")
            stream_producer.timeseries.buffer.publish(df)

    def on_stream_received_handler(stream_consumer: qx.StreamConsumer):
        stream_consumer.timeseries.on_dataframe_received = on_dataframe_received_handler

    topic_consumer.on_stream_received = on_stream_received_handler
    print("Listening to streams. Press CTRL-C to exit.")
    qx.App.run()
    ```

11. Tag the project as `process-v1` and deploy as a service (watch the [video](#watch-the-video) if you're not sure how to do this).
12. Monitor the logs for the deployed process.

## Generate a CPU spike

You can generate a CPU spike by starting up several large applications. In the logs you will see a message similar to the following when a spike is detected:

```
CPU spike of 71% detected!
```

## 🏃‍♀️ Next step

Create a destination to log events and send a notification SMS!

[Serve your data :material-arrow-right-circle:{ align=right }](./serve-sms.md)
