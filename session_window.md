---
title: "Session Window"
tags: ["data","streaming","dp203"]
---

# Session Windows

- A window type used in [streaming][streaming]

- Group events that arrive at similar times

- Filters out periods of time where there is no data

- Windows are constantly being re-evaluated based on when events enter or exit the window

- If, after a set period of time, no data has been received, a window will close and another will open

- Each time a piece of data is received, the window will be held open longer

- The maximum windows size is 7-days

[streaming]: ./azure_stream_analytics.md
