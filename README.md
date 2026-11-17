# San Juan Capistrano Live Trains

A responsive live dashboard that pairs station cameras at San Juan Capistrano and Fullerton with real-time train arrivals, countdowns, delay status, and track information.

## Features

- Switchable San Juan Capistrano and Fullerton station views
- Embedded YouTube livestream for each station
- Metrolink and Pacific Surfliner arrivals filtered to the selected station
- Estimated arrival times and minute-by-minute countdowns
- Schedule variance, service status, destination, and track details
- Two-hour recent-train history saved in the browser
- One-click camera rewind to a recent train's estimated arrival, with one-minute earlier/later adjustments
- Automatic refresh every 60 seconds
- Responsive layout for desktop and mobile screens

## Data sources

- [San Juan Capistrano live camera](https://www.youtube.com/watch?v=-g1qAvXyIyQ)
- [Fullerton live camera](https://www.youtube.com/watch?v=oKwiQBAkEVU)
- [Metrolink Train Tracker](https://metrolinktrains.com/train_status/#tab=train%20status&filter=station&option=San%20Juan%20Capistrano)

Arrival estimates come from Metrolink's public real-time station schedule feed. They are estimates and may differ from the camera by several minutes, so replay controls let you move one minute earlier or later.

Recent trains are retained locally after this page observes them. Camera replay depends on footage still being available in the YouTube livestream's DVR window.

## Run locally

The site is buildless and has no package dependencies. Serve the `dist` directory with any static HTTP server:

```bash
python -m http.server 4173 --directory dist
```

Then open <http://localhost:4173>.

## Structure

```text
.
├── .openai/hosting.json  # Sites deployment configuration
├── dist/index.html       # Complete dashboard application
└── README.md
```

## Deployment

The repository is configured as a static OpenAI Site with `dist` as its published directory.
