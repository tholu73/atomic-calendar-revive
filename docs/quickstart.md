---
layout: default
title: 🚀 Quick Start
nav_order: 1
---

# 🚀 Quick Start

This quick start guide will take you through the easiest ways to get up and running

## Installation

### HACS (recommended)

Install using `HACS` component:
1. You need HACS installed and configured
2. Go to Community tab, Settings
3. Paste this line into `Add custom repository` field:
```
marksie1988/atomic-calendar-revive
```
4. Choose type: Plugin
5. The atomic calendar revive component will be available to install under the Plugins tab.
6. Add the below to the raw configuration editor or to the `ui-lovelace.yaml` file :
```yaml
resources:
  - url: /community_plugin/atomic-calendar-revive/atomic-calendar-revive.js
    type: module
```

### Manual

1. You need to have the [Google calendar](https://www.home-assistant.io/components/calendar.google/) component configured in Home Assistant.
2. Download `atomic-calendar-revive.js` file from the `dist` directory to `/www/community/atomic-calendar-revive/atomic-calendar-revive.js` directory in your Home Assistant - [latest release](https://github.com/marksie1988/atomic-calendar-revive/releases/latest)
3. Add this reference to your `ui-lovelace.yaml` file:
  ```yaml
  resources:
    - url: /community_plugin/atomic-calendar-revive/atomic-calendar-revive.js
      type: module
  ```
4. If you use Lovelace and want to use the editor, download the `atomic-calendar-revive-editor.js` to `/www/community/atomic-calendar-revive/`. (or the folder you used above)
5. Add the card to the UI using the GUI editor or to `ui-lovelace.yaml` with options, examples below
6. If you are upgrading, try to reload your browser cache by pressing ctrl-shift-r or shift-F5.
7. If you want to use `Calendar mode` follow the guide [here](#more-than-5), because by default HA only gets the 5 nearest events from Google Calendar.

## How to show more than 5 events {: #more-than-5 }
In order to increase the amount of events that are shown you have to add `max_results` setting to `google_calendars.yaml` file

For calendar mode we recommend that this is set to at least 30
```yaml
- cal_id: xxxxxxxxxxxxxxxxxxxx@group.calendar.google.com
  entities:
  - device_id: calendar_id
    name: Calendar_name
    max_results: 30
```

## Configuration

For more configuration options check out [this section](https://marksie1988.github.io/atomic-calendar-revive/configurations.html)

### Simple configuration:
```yaml
- type: "custom:atomic-calendar-revive"
  entities:
  - entity: calendar.YOUR_CALENDAR_HERE
    titleColor: red
    whitelist: 'word1,word2'
  - entity: calendar.YOUR_CALENDAR1_HERE
    blacklist: 'word1, word2'
```
