# Overview

[InfluxDB](https://www.influxdata.com/products/influxdb-overview/){target=_blank} is an open-source time series database. It is used for storage and retrieval of time series and event data in fields such as operations monitoring, application metrics, Internet of Things (IoT) sensor data, and real-time analytics.    

Quix currently supports the following connectors for InfluxDB:

| Influx version | Connector type | Description |
|----|----|----|
| [InfluxDB 2.0](https://github.com/quixio/quix-samples/tree/main/python/sources/InfluxDB-2.0){target=_blank} | Source | Enables you to publish data from InfluxDB v2 into a Quix topic. |
| [InfluxDB 3.0](https://github.com/quixio/quix-samples/tree/main/python/sources/InfluxDB){target=_blank} | Source | Enables you to publish data from an InfluxDB v3 bucket into a Quix topic. |
| [InfluxDB 3.0](https://github.com/quixio/quix-samples/tree/main/python/destinations/InfluxDB){target=_blank} | Destination | Enables you to publish data from a Quix topic into an InfluxDB v3 bucket. |

Note if you want to move data from InfluxDB v2 to v3 you could use the v2 source and v3 destination to do this.

<div>
<a class="md-button md-button--primary" href="../influxdb/quickstart.html" style="margin-right:.5rem;">Try the Quickstart</a>
<br/>
</div>
