# Quix product changelog

This is the changelog for the current year. Changelogs for previous years can be found [here](#changelog-archives).

## 2023-12-02-fe-bugs | 11 DECEMBER 2023

`IMPROVEMENTS`

- Organization Homepage
    - Sorting environments in Project cards based on status - moved “non-ready” environments to the bottom
- Applications
    - IDE no longer scrolls to the top after committing changes to a file
- Deployments
    - Improved “skipped” message in *Messages* tab - (we made it sound like we threw your topic messages in the bin)
- Code Samples
    - If searching with a filter applied yields no results: empty state message and CTA changed to *clear* applied filters
    - Enabled “+ Add new” button in topic input field
    - Various loading spinners on CTAs to improve click-action feedback
- YAML
    - Improved supplementary message on syncing with 0 changes to inform user that no changes are made during sync
    - Editing YAML retains carat position (if you click on the YAML section you want to edit before you click edit, then we take you there)

`BUG FIXES`

- Organization Homepage
    - Prevent “undefined” repository issue when switching in and out of projects too quickly
    - Prevent “login required” error in ungated experience
- Data Explorer
    - Waveform was disappearing if you came from *Live data*
- “Topic created” notifications weren’t taking the user to the *Topics* page
- Deployments
    - Deployment dialogue sliders for *CPU* and *Memory* were using the wrong increments
    - *CPU* and *Memory* metrics weren’t cleared when switching to a stopped deployment
    - Destinations were appearing as Transformations in *Lineage* views
- Pipeline
    - Changing topic on a deployment wasn’t updating the pipeline view
    - Adding replays from placeholders didn’t use the correct topic
    - Link for *Public URL* on deployment cards weren’t pointing to the *Public URL*
- Applications
    - Uploading and replacing file wasn’t working
    - Progress bars on *replays* in the *Lineage* tab weren’t moving
    - Heartbeat connection was not reconnecting after disconnection, and it was calling a V1 endpoint
    - Topics being created when user was adding variables
- YAML
    - *YAML* was appearing in edit mode when *YAML* was loading
    - Switching environments when viewing the *YAML* was not updating the environment variables in the *variables* tab
    - Error in sync dialogue was clipping code
- Various component-interaction console errors
- Error messages in various dialogues were persisted
- Updated tab names related to domain changes
- Various UI width fixes

## 2023-12-01-f1 | 7 DECEMBER 2023

`IMPROVEMENTS`

- Deleting old trial workspaces 7 days after disabling

## 2023-12-01-freetier | 6 DECEMBER 2023

`IMPROVEMENTS`

- Increase quotas for free and base tier
- Update trial expired email and delete trials according to that
- Remove unneeded IDE PVCs possibly costing lot

## 2023-11-03-promocode | 16 NOVEMBER 2023

`NEW FEATURES`

- Data explorer: Multi-clause selection for “where” and “group by”
- Replays: Ability to specify start/end timestamps
- Promotional code redemption feature added to the billing page

`IMPROVEMENTS`

- Improved performance of Topics page using virtual scrolling and reducing the amount metrics subscriptions.
- Added new option on Topics page to filter out External topics from the list
- Improved performance of Topics synchronization with external brokers.
- Introduced a tooltip that displays backend error for environments that failed to create
- Improved various CTA loading states
- Improved general performance when running/stopping deployments
- Maintain the selected side nav option when switching between environments
- Platform domain migration from .ai to .io
- Several improvements for BYOC installations
- Added * feature to permissions system Scopes

`BUG FIXES`

- Fixed a bug building deployments that use Open Computer Vision library
- Fixed a bug where IDE Sessions were not detecting errors when installing Python dependencies
- Fixed a bug where some environments get stuck in a Pull-and-push mechanism indefinitely
- Fixed intermittent “Session ApplicationID not found” errors when using online IDE
- Fixed a bug where binary storage for Persisted streams was not working properly for stream/parameters Id’s containing special characters
- Broker test validation was not detecting some permissions issues reading Topic descriptions
- Topic synchronization exceptions on the Environment creation were letting the environment in an Error state
- Billing page was not visible for some Admin users
- Topic Replication Factor was not populated correctly when synchronizing topics from external brokers
- Deployment details weren’t updating the url when navigating through lineage
- Some drawers weren’t closing when a user clicked away
- Branches created externally were not immediately selectable from the change branch dialog of an environment.
- Some Git errors were not cleaned properly after recovering connectivity with the server.
- Topics dropdown icon was misaligned
- Unable to open an application that was renamed
- Disabled replays for streams with no data
- Fixed docs links throughout the platform

## 2023-11-02-brokers-hf | 10 NOVEMBER 2023

`BUG FIXES`

- Broker configuration test was not detecting a lack of read permissions on topics.
- Creation of the environment was failing in some cases when Topics synchronization was enabled.

## 2023-11-01-brokers | 2 NOVEMBER 2023

`IMPROVEMENTS`

- Disabled billing/prices for BYOC users
- Updated behavior of *run* button in applications for ungated users
- Code samples progression stepper updated
- Brokers
    - Updated copies of broker setup guides
    - Added default cluster sizes for Redpanda and Aiven
    - Added new toggle to config panel for managed and self-hosted Redpanda connections
    - Added file validation to only allow users to upload zip, pem, or cert files for the CA certificate
    - Re-enabled cluster size toggles for Redpanda and Aiven
    - New default values for topic configuration based on broker types
- Redacted logs that contain secrets
- Made the PAT token field skinnier

`BUG FIXES`

- Data explorer
    - Search field was clearing when switching to live
    - Removed redundant query to telemetry
- Applications
    - Run config was out of sync with env variables
    - “Branch to edit” button was selecting the wrong commit
    - Converting a hidden variable to a secret was not displaying in redeploy deployment dialogue
    - Output topic was visually missing in deployment dialogue
- Deployment details
    - Lineage disappears when websocket connections fail
- YAML
    - -1 retention in topics was setting as -60000.
- Platform
    - Workspaces were stuck in “creating”/”updating” status
    - Topic quota logic caused external topics and topics that failed to create to count towards organization quotas
    - StreamPackageType changed so icons for data types in messages weren’t being displayed correctly
    - Changing to a locally-created branch was not displaying backend errors
    - Resolved various console errors caused by Front-End component interactions

## 2023-10-04-redpanda | 25 OCTOBER 2023

`NEW FEATURES`

- Environments
    - Brand new RedPanda and Aiven broker settings setup on the environment creation

`BUG FIXES`

- Environments
    - Fixed a bug where the High-Performance selection was forcing users to Enter payment for non-trial tiers
- Data Explorer
    - Adding new parameters in the persisted data query was cleaning Table view incorrectly.
- Pipeline
    - Fixed a bug where the Deployments URLs were not working on the Pipeline view

## 2023-10-03-byoc-hf | 19 OCTOBER 2023

`BUG FIXES`

- Replay Service
    - Tags present in a Parameter and Event at the same time were not replayed correctly on the Events side.
- Data Explorer
    - Fixed exception “The channel has been closed” in some race conditions during Topic closing.
    - Tags on events were not returned correctly when there were duplicate tag names

## 2023-10-02-byoc | 18 OCTOBER 2023

`NEW FEATURES`

- Onboarding
    - Project/environment creation
        - 1 step onboarding auto-creates a project and environment and sends user directly to pipeline with 1 click
        - optional advanced setup takes users to regular project & environment creation flow
    - “Upgrade” button on premium storage to allow users to sign up to serverless and select premium storage during onboarding

`IMPROVEMENTS`

- Environment creation
    - Improved copy of storage settings → “Data and streaming services” and introductory text
        - Tooltips on storage option cards to add usage context
        - “Premium storage” → “High performance”
    - Behaviour of ***tab*** key-press on input fields
- Data explorer
    - Live view now preserves previously selected options
    - Improved general performance and stability of underlying Live data services to support high volumes of data and subscriptions.
- Applications
    - Branch dropdown UX improvements
    - Improved overall performance of commit history component
- Deployments
    - Escaping Build arguments coming from environment variables to remove vulnerabilities
    - Delete deployment dialogue alignment
- Topics
    - Topic configuration can be updated now via YAML file.
- Secrets
    - General UX enhancements on secrets management panel
    - Conflict error handling to prevent users from overriding each other’s changes
    - Secret key on YAML is now called “SecretKey” instead of usual “Value”
- Projects
    - Removed “retry” button in YAML for failed syncs, and replaced with “roll back” or “sync to latest” (the latter for when a user corrects their yaml and wants to sync again)
    - Improved YAML parsing to maintain the order of elements during merging and syncronization.
    - YAML variables definition in the code can now be composed by a combination of text or multiple variables. (ex: “{variable1}-sometext-{variable2}”)
    - Loader on branch dropdown when switching branches for an environment
    - New organization homepage Projects/Environments counters
- Other
    - Autofocus behavior improvements to input fields on onboarding
    - Improved FE performance by changing the way angular components are interacted with
    - Topic component now saves input if a user clicks away from field (previously changes were cleared and confusing users)
    - Added advanced configuration to the Replay service API allowing special reading and writing tunning for some specific use cases.
- Internal:
    - Several improvements to enable BYOC releases
    - Social signup removed for BYOC users
    - Improved Build Service startup time
    - Upgraded service base images to remove vulnerabilities
    - Removed some spammy logs on Deployment service and Workspace service.
    - Improved Git error handling during merges
    - Attached metadata information to the list of files returned by Git service
    
`BUG FIXES`

- Pipeline
    - Fixed a bug where topic metrics were frozen in certain stressed situations.
- Applications
    - Run button in run configuration was not running the application if there were no changes to topics
    - Branch dropdown is now disabled when an operation is in progress to avoid branch-switching issues
    - Cross button during add/rename file was not saving changes
- Deployments
    - Fixed UI crashes when deployment metrics are broken
    - Fixed a bug that was preventing to edit state management configuration
    - Replica warnings were not updating when changing topics
    - Edit deployment modal was showing latest commit regardless of version deployed
    - Fixed a bug where topic metrics were not unsubscribed when switching environments
    - Variables of type Secret that are not Required are no longer raising an exception if the secret is missing in the environment.
- Replays
    - Replay configurations are now persisted in the platform reloading them automatically after service shutdown.
- Projects
    - Don’t stop project deletion if the repo has already been deleted
- Data Explorer
    - Messages were disappearing when a filter was applied on Live data
    - Some data explorer timestamps were being displayed 1/1000th of a second behind
- Other
    - Various fixes to external URLs on platform
    - Fixed some incorrectly handled errors on Streaming Writer service
    - Fixed an issue causing “Exceeded memory limit for $group" exception when querying persisted data with a big number of parameters (>3000).
- Internal
    - Fixed some issues related to tokens and permissions of the platform
    - Fixed some CORS issues on Portal backend
    - Fixed an issue in the Update versions service where the workspace update was failing during Creation or Deletion of the workspace.

## 2023-10-01-deployment-hf | 3 OCTOBER 2023

`IMPROVEMENTS`

- Added unsaved changes dialogue to YAML variables
- Pipeline cards for deployments now show number of replicas

`BUG FIXES`

- Deployment dialogue was overwriting deployment config with default values when editing
- “+ New environment” for users whose trials have run out was not showing correct dialogue
- Fixed enable buttons on organization homepage for:
    - environment cards
    - project card context menus
- Removed unnecessary calls to secrets endpoint
- Messages in data explorer were looking like they were disappearing

Second release under tag release/2023-10-01-deployment-hf-2:

- Settings page was broken for V1 workspaces

## 2023-09-07-ws-service-fix | 29 SEPTEMBER 2023

`BUG FIXES`

(Internal) Workspaces with no services should properly re-install

## 2023-09-06-ungated-fixes | 28 SEPTEMBER 2023

`NEW FEATURES`

- Added Repository level scope to the permission system

`ENHANCEMENTS`

- Updating the Ungated Experience user menu and banner
- Added spinners on git operations in the IDE
- Message tab subscriptions is only enabled when you open the Messages tab
- Increased Trial tier quotas to allow 2 projects, 4 environments, 8 cores, 16 GB memory, 40 replicas

`BUG FIXES`

- Deep links to deployments weren’t working sometimes
- Unable to use URLs in environment variables free text when adding
- Topic subscriptions not updating when switching environments
- Renaming entry-point file removes entry-point status
- Retention period was not updated correctly when the retention periods higher than 30 days.

## 2023-09-05-v2-hf | 26 SEPTEMBER 2023

`ENHANCEMENTS`

- Hide “Users” tab for ungated experience
- Removed business exception on getting Users
- Removed RegEx on application creation

`BUG FIXES`

- “Sign up for free” button was not logging users out
- YAML empty state misaligned
- Minor typos

## 2023-09-05-v2 | 25th SEPTEMBER 2023

`NEW FEATURES`

- **V2 is now default for everyone**
- Modal to format application name and path from Code Samples
- Applications can be created in subfolders
- Temporary token is available to all users

`ENHANCEMENTS`

- Increased Premium tier resources and SSD disk types on Serverless
- Improved Memory and CPU consumption of Replay service on big workloads (Replay service)
- Improved Memory and CPU consumption of Streaming Reader service on big workloads (Live data explorer)
- Added Start and End date-times properties to Replay service API
- Added deployment name to browser tab
- Decreased opacity of expired tokens to improve visibility
- Quix V2 (IaC):
    - Improved build system to not rebuild images that belong to the same repository (aka Project)
    - Git errors handling improvements. The service now cleans automatically connectivity errors after a successful Fetch.
    - Increased Secrets security encryption to 256 bits
    - Added menu in environment settings
    - Refresh branches button in branch dropdown during environment creation
    - Added RegEx to secrets management
    - FE valiation on public URL to align with K8s limits
    - Back arrow when creating an environemnt from project settings takes you back to project settings (previously was sending users to org homepage)
    - Deployment environment variables will now reflect the variables related to the specific commit reference
- Internal:
    - Several improvements to enable BYOC releases
    - Increase K8s Requests to 25% of the limit of the Deployment
    - Upgrade Quix Streams version to 0.5.6 in all the services
    - Some adjustments applied to the tier Quotas
    

`BUG FIXES`

- Streaming permission added (legacy) in addition to Stream
- Fixed a bug deleting tags and branches that contain “/” character
- Fixed a bug where user Profile was not saved correctly on old users
- Fixed a bug where Persisted topics were not persisting data from the beginning of the Kafka topic
- Sync topics in external kafka was always sending “true”
- Quix V1
    - Unable to deploy from a branch
- Replay service
    - Fixed a bug where Close stream event was not being sent at the end of the replay
    - Fixed a bug where Parameter definitions were not sent in some use cases
    - Fixed a bug where target StreamId was not assigned property when replaying multiple streams
- Quix V2 (IaC):
    - Delete a Project was not deleting secrets
    - Historical commits weren’t showing as read-only
    - Fixed issues regarding tags and missing applications
    - Minor typos
- Internal:
    - Some bug fixes applied to the Workspace services update system
    - Several small fixes on the permission system to handle some edge cases

## 2023-09-03-secrets-hf-2 | 11 SEPTEMBER 2023

`BUG FIXES`

- PAT in URL feature was breaking FE because of a google tag in the URL
- Adding V2 feature back to prod
- Replays were not sending parameter definitions in subsequent replays
- Logic for multiple replays were not working

## 2023-09-02-secrets-hf | 11 SEPTEMBER 2023

`BUG FIXES`

- Google tag in URL was causing FE to break
- Quota for Early adopter trial was incorrect

## 2023-09-01-secrets | 7 AUGUST 2023

`NEW FEATURES`

- Onboarding for V2 on mobile & desktop
- Secrets Management:
    - Save your password and sensitive data in Quix and use them securely in your Builds and Deployments.
    - New variable type Secret where you can assign a Secret and send it securely to your deployment without exposing it to any user of the platform.
- Ungated Experience:
    - Portal accepts PAT as a URL parameter to log in
    - New banner and “Sign up” CTA
    - Modified profile image, name, and context menu options
    - Snack bar appears for unauthorised actions
    - Requires “Guest” flag on user - Configuration details for setup can be found here (link coming soon)
- Trial length set to 30 days (previously 90)
- Added the ability to send Variables to the Docker Build process as dockerfile arguments (ARG)
- New Backend Permission system as a base for the new ungated experience and future Frontend permission system
    - Includes changes to all services to validate operations

`ENHANCEMENTS`

- Improved the Build logs information shown on the Deployment details page
- Maintained deployment logs for services stopping and starting to give better visiblity in deployment details
- Disabling of inputs in creation modals when form is in progress
- Signup page now accepts as redirects to the sign up page
    - /signup
    - /sign-up
    - /self-sign-up
- V2 Closed Beta:
    - SSH Key per Repository. Now we are creating a different SSH Key per Repository to avoid issues with providers like GitHub.
    - Added new dialogs and notifications to inform the user about communication problems between Git service and the Git repository (ie. connectivity issues, permissions, etc)
    - Improved behaviour of file tree in Applications IDE
    - Improvement of Git error displayed in the environment creation flow
    - Added RegEx to Yaml variables
    - Removed side options in Applications list page and changed “New application” CTA options
    - Improved visibility of Git credentials and PR UX
    - Creading Applications from Code Samples displays modal to format name and application path
    - You can now use a forward slash “/” in tags and branch names
    - 
- Internal:
    - Added a new updater service system that simplifies the release process
    - Increased resources for some of the Workspace services by default to improve the stability for standard workspaces, and Added some Requests configuration for Premium workspaces
    - New Quota system introducing new quotas per organization
    - New payment modal explaining serverless when a user clicks on payment CTAs

`BUG FIXES`

- V2 Closed Beta:
    - Several fixes and enhancements in the Git Service implementation
    - YAML/Sync
        - Order of the items on the YAML synchronization when merging environments
        - Fixed an issue where a Syncronization process can fail while editing a deployment with an existing UrlPrefix
        - Disabled “New Yaml” button for empty state in protected environments
    - Applications
        - Variables disappearing in some use cases
        - URLs were not being encoded in network requests
        - Incorrect source branch selected in branch creation modal
        - Added scroll to environment variable section
        - Fixed issue with renaming files
        - Restart session was leaving us in a session-less state wen switching branches
    - Deployments
        - CPU and memory limits were showing incorrect values when using replicas
        - Edit deployment modal was not loading tags created in a session
        - Renamed applications and their respective tags weren’t appearing in edit modal
        - “In use” column was not showing any usage values
        - Fixed various buttons not opening replay/persisted streams etc in deployment details and lineage
        - Removed the “Next” button in deployment dialogue when there are no more steps
        - Package types were showing as “undefined” in deployment messages
        - Added backend validation to URL prefix lengths to prevent going above Kafka limit
- Fixed some stability issues and logs improvements on Replay service
- Deleting files in V1 Projects was returning
- Removed some V1 page calls going to V2 endpoints
- Fixed various RegEx loops around the platform
- Various padding changes:
    - For longer names to improve visibility of options and CTAs falling off the end
    - Dodgy alignment of error messages, and CTAs
- Disabled and added tooltips to various unavailable options in context menus throughout the platform, and removed obsolete ones
- Fixed empty state appearing when pipeline was loading
- General typos
- Removed errors persisting in some modals (More fixes in this area to come FYI)
- Code sample icons going missing

## 2023-08-03-IaC-2-hf-2 | 10 AUGUST 2023

`BUG FIXES`

- Live messages were not working on Data Explorer when navigating from Deployment details
- Fixed an issue on the Streaming Writer service when using the same stream Id on different topics.
- Fixed an issue when edit an existing deployment causing the environment variables not being loaded in the UI

## 2023-08-02-IaC-2-hf | 3 AUGUST 2023

`BUG FIXES`

- Latest commit number wasn’t appearing in the add/edit deployment details for V1
- Commit number dropdown wasn’t appearing in the add/edit deployment details for deployments from Code Samples in V2

## 2023-08-01-IaC-2 | 3 AUGUST 2023

`ENHANCEMENTS`

- Icons for Quix and other git providers in Environment creation
- Applications:
    - Migrated ngx-monaco-editor to V2
    - Adding/deleting tags no longer requires page refresh
    - Code is automatically committed when pressing the *Run* button
    - app.yaml is now a protected file
    - Renaming of files and character validation
    - Refresh button to get latest changes from git
    - Confirmation dialogue when deleting a branch
    - Dependencies are installed upon opening the application
- Inviting a user to an organization now displays a “pending” or “error” status
- README files are selected by default in *Code Samples*
- Deployments are no longer auto-focused after deploying (it was getting annoying)
- Minor enhancements in dropdown behavior during query selection in the data explorer
- Background colours for Applications and YAML when an env is protected or out-of-sync
- Improved error handling of the Git Service
- Better handle of auth0 exceptions when creating a user
- Added the ability to modify an Application of a Deployment from YAML file
- Pull requests are now made under the user that is logged into the portal (previously it was all under “root”)

`BUG FIXES`

- Fixed various issues in the IDE regarding:
    - errors in console logs
    - running incorrect versions of the code
    - “save changes” dialogue
    - editor complaining when files contain emojis
- Multiple modals appearing in the YAML
- Replay name and stream ID is now prepopulated when generating a replay from *Persisted Streams*
- *Page View* events were missing in PostHog
- Minor UI changes to elements not displaying correctly
- Deleting deployments from the *Deployments* page was redirecting to the *Pipeline*
- Deployments with no topics were blending in with the *Pipeline* background
- Backend:
    - Users weren’t being deleted from *Gitea* when deleting in *Portal*
    - Fixed some issues when installing *requirements.txt* in *python*
    - Deleting an organisaion with an admin endpoint was throwing an exception
    - Quix reports weren’t working since last release
    - In some cases, we were raising out-of-sync incorrectly while using the platform
    - Confluent partnership Id was not sent properly when using the platform

## 2023-07-03-IaC-post-fixes | 19 JULY 2023

`BUG FIXES`

- Fixed an issue regarding Code Samples library builds. Some of the builds were not present in the history retrieved from the Git repository.
- Fixed an issue Installing requirements of an IDE session when the Git Service under the hood was previously restarted.
- Fixed Streaming Writer logging issues
- Fixed some issues when running Projects in v1
- Empty YAML state was allowing to press the buttons in Protected mode
- When synchronizing from YAML some Deployments version was shown as full SHA commit reference in deployment details.
- Link to Git on Manage Git Credentials was pointing to an incorrect url
- Link to Latest Commit in IDE was not updating file list.

## 2023-07-03-IaC | 19 JULY 2023

`NEW FEATURES`

- Quix as Code (aka Streaming Pipelines as Code)
    - Protected environments - UI signals, snackbars
    - Yaml and context menu
        - Synchronization (bi-directional)
        - Sync status
        - Empty state - Generate from pipeline, create new
        - YAML variables
    - Environment
        - Synchronization (bi-directional)
        - Sync status
        - Top nav environment selection and context menu
        - Branch selection
            - Branch creation dropdown
        - Merge
            - Direct merge
            - Pull request
        - Applications (IDE)
            - New IDE Sessions architecture for faster and more reliable response times
- Git
    - New Quix managed Git service using Gitea
    - External git - users can now connect to their own git repository
- Project settings
    - Configure which branch is used for which environment
    - Generate Gitea credentials for Quix-managed repositories
- User Menu
    - Git credentials for Quix-manages repositories
- Added Non-QuixStreams formats compatibility in all our observability services.

`ENHANCEMENTS`

- Added pickle, pkl, ctf, files to the no-render list in the IDE
- Git repo cards are now disabled while environment creation is in progress (you could click around them before)
- JSON string of a parameter can be viewed in the Data Explorer table view
- Topics containing non-quix format data is now viewable
- Updated the tag order of code samples in filters
- Topic cards in the deployment details now show a “creating” status if the topic isn’t ready yet
- Clicking “Edit code” in a code sample takes you directly to a newly created application (V2 ONLY)
- Added “client.id” property to some of our services to track Quix Kafka usage on external providers like Confluent.
- Added the ability to set special Quotas per Organization
- Improved internal Quix reports with more information
- Deployment details
    - Replica display is now based on deployment type (job/service). Running a job multiple times no longer displays replicas of previous jobs.

`BUG FIXES`

- Fixed some issues on Deployments when using special characters inside environment variables values
- You can no longer edit your own roles
- Deployment details: Logs
    - Build logs will no longer appear in the deployment logs when you switch tabs
    - Deployment logs weren’t being displayed when changing tabs because of a error in the network call
- Various fixes for long names escaping containers
- UI fixes for Firefox users

## 2023-07-02-skip-hf | 11 JULY 2023

`BUG FIXES`

- Fixed issue regarding skip button context

## 2023-07-01-posthog | 6 JULY 2023

`ENHANCEMENTS`

- PostHog is now enabled for our portal
- “Skip” button is available during the onboarding questions
- Streaming Reader Packages subscriptions is now rate limited to 10 packages per second

`BUG FIXES`

- Fixed several issues regarding replaying persisted streams
- Fixed an issue when editing a user was changing profile context

## 2023-06-03-build-hotfix | 15 JUNE 2023

`BUG FIXES`

- GPG key bug fixed

## 2023-06-02-frontend-hotfix | 1 JUNE 2023

`BUG FIXES`

- Hidden environment variables for firefox were not hiding anymore (firefox removed the support for the class we were using)
- Project tags shown as “missing” in deployment details (added call to get tags when navigating to the deployment details)
- Replica warning tooltip was using replication factor, not partitions
- Pipeline was breaking when we had undefined values in draft projects

## 2023-06-01-post-billing-fixes | 13 MAY 2023

`ENHANCEMENTS`

- Prevent binary files from being loaded in the front end IDE (no more weird symbols)
    - Prevents Simulink files from being corrupted
- Disabled premium storage for trial users
- Updated premium storage prices
- Increased disk memory on Build service to allow bigger images

`BUG FIXES`

- Preventing deployment logs leaking into another deployment
- Fixed a bug in Replay service that was causing some streams not being replayed
- Data explorer
    - ********group-by******** was assigning multiple groups under one group
    - Visualising a persisted stream was staying in a loading state (local storage wasn’t updating)
- Migrating users that fell out of the previous migration to trial because they didn’t have any tier in the database
- Preventing error messages from being displayed for disabled users (the disabled state means a user cannot do anything on the platform but the back end didn’t like it and was showing toasters)

## 2023-05-02-billing | 24 MAY 2023

`NEW FEATURES`

- New Invoice billing system + Trial updates
    - *****Trial***** - It is fixed to 90 days or $300 credits ($330 for current Free users ) whichever runs out first
    - **********Serverless********** - users who upgrade with payment card with Stripe that sends monthly invoices to user based on usage
    - Disable account improvements based on the new Trial and Invoice billing requirements
    - New Billing page with new design and support for the new Invoice billing system
    - Improvements on the migrations process of the current Free users (Free → Trial)
- New workspace settings page with:
    - General settings, Broker Settings, API & tokens
    - Workspace details: workspace name, ID, creation date, broker type, and storage.
    - Broker Credentials
    - API and Streaming tokens
- Topic Retention can now be specified in bytes (topic size)
- New real-time deployments metrics system for more
- New deployments Replica selector on Deployments detail page
- Ability to select between Broker timestamps and Data timestamps in the Message explorers
- Binary parameter support in Persisted data explorer
- New Workspace dropdown menu with recently visited workspaces
- 

`ENHANCEMENTS`

- Redesigned top-right profile menu with Users, PAT Tokens and password change options
- Refactored PAT tokens page and dialogs
- Enhanced headers and menus of the platform to accommodate  features coming in the subsequent releases
- Improved real-time Deployment logs behavior
- Replica increase warnings for topics with fewer partitions than the deployment replica number
- Replaced “SDK” with “Quix Streams” in the whole platform
- Deployment details UI/UX improvements
- ZIP download option on Persisted Data Explorer
- Mobile carousel for onboarding
- Improvements to highlight when a Tag is missing in Git
- Online IDE enhancements (new deployment component, improved Setup session and others)
- Several UI fixes in the whole platform
- Removed license agreement modal (we send this in the emails)

`BUG FIXES`

- CPU values are divided by 1000 each time you edit and cancel a deployment.
- Fixed several issues on the Online IDE file explorer
- Stop a deployment is waiting now for the completion of the stopping process
- Updating a deployment while a deployment was stopping was causing the deployment update get stuck in Building state.
- After a deployment update some builds were cleaned incorrectly.
- Branch selection was not selecting the last commit when a reference of a specific commit/tag is set.
- Setting console/messages/data lineage to display run config values (instead of environment values)
- Fixed several issues regarding Users/Admin roles.
- Billing page is stuck to the loading state when the organization is not consuming credits.
- Several minor fixes in Persisted Data Explorer when querying and interacting with the UI
- Several fixes applied in Replay service feature
- Fixed several tooltips of the platform
- Applying character limits to input fields
- Local storage of workspace and organization has been improved

## 2023-05-01-HF | 11 MAY 2023

- Fixed “Delete user” button showing edit user dialogue

## 2023-04-01 | 13 APRIL 2023

- 90 day free trial and upgrade button

## 2023-02-03-hubspot-hotfix | 4 APRIL 2023

- Frontent code was not connecting new user activity from marketing side to SaaS.

## 2023-02-03-HF2 | 10 MARCH 2023

- Resolving issues regarding signups
- Resolving exception handling in services
- Preventing users from deleting the last user (themselves)

## 2023-02-03-HF1 | 6 MARCH 2023

`NEW FEATURES`

- Removing payment values for free users for broker settings in onboarding and workspace creation

`BUG FIXES`

- Overlapping UI on long topic retention values
- Topic errors leaking to other modals
- Branch names being truncated in new branch modal
- Library stepper intractable on library page

## 2023-02-03 (self-hosted kafka) | 2 MARCH 2023

`NEW FEATURES`

- New Self-hosted kafka broker workspace configuration. Connect your own Kafka to Quix.
- New Onboarding with new broker configuration options

`ENHANCEMENTS`

- New left side menu preparing the UI for future features
- New authentication system for future on-prem solutions
- Topic configuration improvements
- API tokens improvements
- Create new topics in topic dropdown component for project deploy modal
- Switchers are now non-interactable in loading state
- Topic errors are now exposed on Topics view
- Small UI / UX improvements

`BUG FIXES`

- Tooltip now disappears when no longer hovering on element
- Improved pipeline view behaviour
- Topic speed metrics are now more reliable
- Error state topics are no longer displayed in Persisted Streams
- Disabled email address field on user details edit
- Disabled visualise button for persisted streams with no data

## 2023-02-01-HOTFIX-3 | 14 FEBRUARY 2023

- Fixed Library showcase (it was missing)

## 2023-02-02 | 13 FEBRUARY 2023

- Dev Rel Docs and Library

## 2023-02-01-HOTFIX | 8 FEBRUARY 2023

- Fixed user being unable to signup to PROD using password and email (Direct Signup) - some issue with google recaptcha 

## 2023-02-01 | 7 FEBRUARY 2023

`NEW FEATURES`

- Updated links for portal Quix Docs site: https://docs.quix.io/
- Direct Sign up
- Increase state limit for deployments (100GB for paid tiers and 1000GB for Quix tier)
    
`BUG FIXES`

- Projects
    - Downloading a *branch* (It used to download *master* instead of the *branch*)
    - IDE History view now shows the file the history is for (previously showed last viewed file)
    - Changes in env variables now reflected in deploy modal
- Library
    - Adding an external source
    - Solved problem with “Quick start” and “Mobility” filters
- Deployment details
    - Variable name validation now on input (previously on CTA click)
    - Adding and editing Topic metrics now update and display in mini-pipline section
    - Missing Parameter names
- Data Explorer
    - Waveform view performance
    - Better waveform display; Pausing and playing no longer causes lines to jump around
    - Parameters and data displayed after reconnecting to web-socket
    - No red click and drag on waveform view (it wasn’t doing anything)
- Other
    - Disabled GTM tracking on Dev
    - Deployment from IDE redirects to Deployment details
    - Topic dropdown now shows all available topics and only filters when you start typing
    - Google reCaptcha can now be disabled without issue
    - Now able to invite users to platform

## 2023-01-01 | 30 JANUARY 2023

`NEW FEATURES`

- Workspace “Disable” option
- “In use” field for Topics to show where they’re being used
- Modal for credit tier limit
- Update status component for deployment status
- Persisted streams icon is disabled when no persisted streams are available
- Upgrade request button for users - allowing them to notify us with an upgrade request in one click

`BUG FIXES`

- Deploy dialog now shows correct save and commit version
- Updated upgrade information in workspace - upselling
- Topics created upon deployment of code (Like Project behaviour)
- Preventing diagram flicker when editing topic from deployment pipline
- Improved deployment status accuracy
- Fixed ReGex for topic names
- Speed indicator being stuck at 100mb/s
- Topics table scroll going beyond header
- Inconsistent table sorting
- Topic error persisting in loading dialog after topic is deleted

## Changelog archives

* [2022](./changelogs/2022-archive.md)
