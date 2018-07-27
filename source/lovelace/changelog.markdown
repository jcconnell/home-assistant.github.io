---
layout: page
title: "Lovelace Changelog"
description: "Changelog of the Lovelace UI."
date: 2018-07-01 10:28 +00:00
sidebar: true
comments: false
sharing: true
footer: true
---

## {% linkable_title Changes in 0.74.0b0 %}

### Views
- Add basic support for `badges` like in old view style
- Custom cards now work with `panel: true`

### Cards
- `glance` card supports now `toggle` and `turn-on` besides showing more-info dialog
- `glance` card supports now to hide `name` or `state`
- `history-graph` supports override of entity names
- Allow `picture-glance` to open more info for camera 
- Show more-info for `media_players` in `picture-glance`
- `picture-elements` card now supports also `image` as element type
- `picture-elements` card now supports also `service-icon` as element type
- Make Lovelace `entity-filter` card more robust (new use case: https://github.com/home-assistant/ui-schema/issues/82)
- 🔧 Fix `picture-glance` crash when state of entity was unavailable

## {% linkable_title Changes in 0.73.1 %}

- Setting Lovelace as default now updates `Overview` button to point to `/lovelace`
- Allow setting background styles (global and per view)

### Cards

- 📣 New card: `map` that allows showing `device_tracker` entities on a map card
- 📣 `entities` card now support `type: custom:state-card-custom` for the entities list

## {% linkable_title Changes in 0.73.0 %}

### Views

- 📣 New button to show unused entities in Lovelace

## {% linkable_title Changes in 0.73.0b5 %}

- 🏁 Only minor fixes in this release

## {% linkable_title Changes in 0.73.0b4 %}

### Cards

- 📣 `picture-entity` allow hiding of infobar using `show_info: false`
- 📣 `picture-entity` now supports `tap_action` parameter allowing you to switch from `on`/`off` to `more-info-dialog`
- 📣 `picture-glance` now supports `navigation_path`
- `picture-entity` renamed `title` to `name`
- `picture-elements` renamed `path` to `navigation_path`
- ‼️ `camera-preview` card removed, features added to `picture-entity` and `picture-glance`

## {% linkable_title Changes in 0.73.0b3 %}

### Views

- 📣 Added panel mode for a view to use the 1st card to fill the whole screen

### Cards

- 📣 New card: `picture` for triggering navigation and services
- 📣 `picture-elements` now supports `navigation` type
- 📣 `picture-entity` now supports `camera_image`
- 📣 `picture-glance` now supports `camera_image`
- 📣 `picture-glance` now supports `state_image` and `entity` like `picture-entity`
- 📣 `entity-filter` now supports custom name for entities like `glance` and `entities`
- `entities` and `glance` custom titles now use `name` not `title`
- `entity-filter` now uses `entities` as a static list to filter state against
- `entity-filter` uses `state_filter` array instead of `filter` object
- 🔧 Fix wrapping and padding for `service-button` in `picture-elements`
- ‼️ `entity-filter` no longer allows to show all entities or a full domain

## {% linkable_title Changes in 0.73.0b2 %}

- :zap: Went by too fast :zap:

## {% linkable_title Changes in 0.73.0b1 %}

### Cards

- `column` renamed to `vertical-stack`
- `row` renamed to `horizontal-stack`
- `picture-elements` new `state-badge` using `ha-state-label-badge`
- `picture-elements` renamed `state-badge` to `state-icon`
- `picture-elements` renamed `state-text` to `state-label`
- `picture-elements` moved/renamed `service.data` to `service_data`
- `picture-elements` combined `service.domain` and `service.server` into `service`
- 📣 `entities` allow custom title just like `glance`
- 📣 `entity-filter` allow auto-hide if empty using `show_empty: false`
- 🔧 Fix card size calculation `horizontal-stack`/`vertical-stack` 

## {% linkable_title Changes in 0.73.0b0 %}

- 📣 New feature to allow Lovelace to be default for `/`

### Views

- 📣 Now views have deep-links: `/lovelace/3` will link to the tab with id `3`
- `name` renamed `title` to match cards setup
- `tab_icon` renamed `icon` for simplicity

### Cards

- 📣 New card: `picture-elements`
- 📣 New card: `column`
- 📣 New card: `row`
- 📣 `glance` allow custom title for entities - rename your entity only in this card
- 📣 `entities` toggle button in a header can now be hidden using `show_header_toggle: false`
- `entity-picture` renamed `picture-entity` to be consistent with `picture-glance`
- `entity-filter` removed `card_config` and made `card` property an object
- 🔧 Fix use of groups in `picture-entity`
- 🔧 Fix the title in `glance` to avoid overlapping

## {% linkable_title Changes in 0.72.1 %}

### Cards

- 🐞 Bug introduced in `glance` card - titles now overlap
- 📣 New card: `iframe`

## {% linkable_title Changes in 0.72 %}

- Initial release of the Lovelace UI
