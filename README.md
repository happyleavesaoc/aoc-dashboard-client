# dashboard-client

Web client component of AoC Spectator Dashboard.

### Architecture

The client consumes a message stream from [dashboard-server](https://github.com/happyleavesaoc/aoc-dashboard-server) via the WebSocket protocol. Each message type is assigned a handler. The client indicates which message types it wishes to receive (subscription). Stream rate is variable. The client maintains 100ms and 1s interval loops independently of the message stream, for updating visual components.

### Message Types

Type | Frequency | Buffered | Description
-----|-----------|----------|------------
start | 1 | yes |
end | 1 | yes |
time | 1/sec | yes | 
map | 1 | yes |
positions | 1-n | yes | n: number of players
title | 1-v | yes | 
heatmap | 1/sec | no | 
apm | 1/sec | yes
player_update | 1/sec | yes | 
research | v | yes | 
research_progress | v | yes | 
research_stop | v | yes | 
trade | v | yes | 
tribute | v | yes | 
chat | v | yes | 
alert | v | yes | 
resign | 0-n | yes | n: number of players


### Dependencies
 - jquery 2.1.3
 - jqueryui 1.11.3
 - [heatmapjs 2.0](https://github.com/pa7/heatmap.js/)
 - canvasjs 1.6.1
 - [progressbarjs 0.7.4](https://github.com/kimmobrunfeldt/progressbar.js)
 - [i18next 1.7.7](https://github.com/i18next/i18next)

### Contribution
 - Pull requests & patches welcome
