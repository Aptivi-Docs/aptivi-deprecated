---
description: How do you use it?
---

# 🖥️ How to use

Using this library is very simple! Just use the `ShoutStats.Core` namespace in any piece of code you want to use the library, as in: `using ShoutStats.Core;`

Once you have the server host name and the port, you can create a new instance of the `ShoutcastServer` class and call either `Refresh()` or `RefreshAsync()` to fetch the following info from the server:

* `ServerHost`
  * Server IP address
* `ServerPort`
  * Server port used by Shoutcast
* `ServerHostFull`
  * Server IP address with port
* `ServerHttps`
  * Whether the Shoutcast server is using HTTPS or not
* `ServerVersion`
  * Server version (1.x, 2.x)
* `TotalStreams`
  * Total number of streams in the server
* `ActiveStreams`
  * Active streams in the server
* `CurrentListeners`
  * How many people are listening to the server at this time?
* `PeakListeners`
  * How many listeners did the server ever get at peak times?
* `MaxListeners`
  * How many people can listen to the server?
* `UniqueListeners`
  * How many unique listeners are there?
* `AverageTime`
  * Average time on any active listener connections in seconds
* `AverageTimeSpan`
  * Average time on any active listener connections in the time span
* `Streams`
  * Available streams and their statistics

Stream information class, `StreamInfo`, contains the following variables:

* `StreamId`
  * Stream ID starting from number one (1)
* `CurrentListeners`
  * How many people are listening to the stream at this time?
* `PeakListeners`
  * How many listeners did the stream ever get at peak times?
* `MaxListeners`
  * How many people can listen to the stream?
* `UniqueListeners`
  * How many unique listeners are there?
* `AverageTime`
  * Average time on any active listener connections in seconds
* `AverageTimeSpan`
  * Average time on any active listener connections in the time span
* `StreamGenre` -> `StreamGenre5`
  * The stream genre
* `StreamHomepage`
  * Link to the stream homepage
* `StreamTitle`
  * Stream title
* `SongTitle`
  * Song title
* `StreamHits`
  * Stream hits
* `StreamStatus`
  * Stream status
* `BackupStatus`
  * Backup stream status
* `StreamListed`
  * Is the stream listed?
* `StreamPath`
  * Path to stream
* `StreamUptime`
  * Stream uptime in seconds
* `StreamUptimeSpan`
  * Stream uptime in the time span
* `BitRate`
  * Stream bitrate in kbps
* `SampleRate`
  * Sampling rate in Hz
* `MimeInfo`
  * MIME info for stream, usually audio/mpeg.

You can use this library to make an application that fetches info from your Shoutcast server for analytical purposes.

{% hint style="info" %}
For web development and other cases where asynchronous code is acceptable, use the Async version of the functions as outlined in the beginning of this page to avoid blocking the main thread.
{% endhint %}
