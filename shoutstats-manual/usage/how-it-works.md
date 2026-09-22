---
description: How does it work?
---

# ⚒️ How it works

When creating a new instance of the `ShoutcastServer` class, it first verifies the Shoutcast server host and builds the full URL of the server.

Then, it builds two URIs:

* Statistics: `<host>/statistics?json=1`
* Legacy Stats: `<host>/7.html`

When the user calls the `Refresh()` or `RefreshAsync()` functions, it checks the first statistics URL to see if it exists or not. If the Shoutcast version is 1.x, this URL will return `Invalid resource` as the response, hence falling back to the v1 parser. Otherwise, the v2 parser takes care of the rest.

## Shoutcast v2 parser

As soon as the response is fetched from the server, it parses the JSON response. It then installs all the available values to the new class instance.

For the streams, ShoutStats iterates through all the streams that the server provides. To extract info from the stream object, a new instance of `StreamInfo` is created for each stream.

## Shoutcast v1 parser

As soon as the HTML response is fetched from the server, the HTML token system attempts to load the HTML response.

The parser then attempts to parse the body and extract text from it, which contains the server information in this format:

```
currentlisteners,streamstatus(S),peaklisteners,maxlisteners,uniquelisteners,bitrate(S),songtitle(S)
```

Finally, it splits this group of variables into their individual values and installs the resulting values to the variables in the new class instance.
