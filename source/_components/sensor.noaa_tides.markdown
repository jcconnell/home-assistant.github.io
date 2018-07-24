---
layout: page
title: "NOAA Tides"
description: "Instructions to add NOAA Tide information to Home Assistant."
date: 2018-07-24 08:00
sidebar: true
comments: false
sharing: true
footer: true
ha_category: Weather
ha_release: 0.75
---

The `noaa_tides` sensor platform uses details from [NOAA Tides and Currents](https://tidesandcurrents.noaa.gov/api/) to provide information about the prediction for the tides for any location in the United States.

This sensor requires the use of a NOAA station id. Search [NOAA Tide Predictions](https://tidesandcurrents.noaa.gov/tide_predictions.html) to find a location. Use the Id from the search results in your configuration. Alternately, you can determine a station id from a URL. For example, `8721164` in the following url `https://tidesandcurrents.noaa.gov/noaatidepredictions.html?id=8721164`

To use this sensor, add the following to your `configuration.yaml` file:

```yaml
# Example configuration.yaml entry
sensor:
  - platform: noaa_tides
    station_id: 8721164
```

{% configuration %}
station_id
  description: ID of the station you'd like to track from https://tidesandcurrents.noaa.gov/tide_predictions.html.
  required: true
  type: string
name:
  description: User supplied sensor name.
  required: false
  default: NOAA Tides.
  type: string
timezone:
  description: User selected timezone.
  required: false
  default: Defaults to local standard / local daylight time.
  type: list
  keys:
    gmt:
      description: Greenwich Mean Time.
    lst:
      description: Local Standard Time. The time local to the requested station.
    lst_ldt:
      description: Local Standard/Local Daylight Time. The time local to the requested station.
units:
  description: Specify the unit system.
  required: false
  default: Defaults to `metric` or `imperial` based on the Home Assistant configuration.
  type: string
  keys:
    metric:
      description: Metric (Celsius, meters, cm/s) units.
    english:
      description: English (fahrenheit, feet, knots) units.
{% endconfiguration %}
