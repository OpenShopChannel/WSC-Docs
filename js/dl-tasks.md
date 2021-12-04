---
description: Banner operations at your fingertips
---

# DL Tasks

As part of WiiConnect24, channels have the ability to register "tasks" permitting occasional download of any sort of file. For example, the Forecast Channel uses download tasks to update its information when idle. Historically the Wii Shop Channel changed its banner via download tasks.

You use a `wiiDLTask` object to interface with WC24 and manage tasks directly from JavaScript.

```javascript
var dlTask = new wiiDlTask();
```

## Members

| Member Name                             | Discussion                                                                                                                                                                                                                                                |
| --------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `dlTask.addDownloadTask(url, interval)` | Adds a task to be downloaded. `url` should point directly to a file within the [WC24 Content](https://wiibrew.org/wiki/WiiConnect24/WC24\_Content#WC24\_encryption) format. `interval` is an integer given in minutes specifying when to repeat the task. |
| `dlTask.deleteDownloadTask()`           | Requests that one task is deleted. It is unclear how multiple tasks would be handled, if that is even possible.                                                                                                                                           |
| `dlTask.hasDeletedDLTask()`             | Verifies the amount of registered tasks is equal to 0.                                                                                                                                                                                                    |
