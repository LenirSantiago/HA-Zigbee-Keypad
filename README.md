# HA-Zigbee-Keypad-Xfinity-xhk1-ue <!-- omit in TOC -->

- [Introduction](#introduction)
- [Installation](#installation)
- [Updating](#updating)
- [Usage](#usage)
  - [Creating a schedule](#creating-a-schedule)
    - [Choosing an entity and action](#choosing-an-entity-and-action)
    - [Choosing the days](#choosing-the-days)
    - [Choosing the time](#choosing-the-time)
  - [Creating a time scheme](#creating-a-time-scheme)
    - [Timeslots](#timeslots)
    - [Time scheme editor](#time-scheme-editor)
  - [Options panel](#options-panel)
    - [Condition editor](#condition-editor)
    - [Period](#period)
    - [Behaviour after completion](#behaviour-after-completion)
    - [Name](#name)
- [Configuration](#configuration)
  - [Options](#options)
  - [Standard configuration](#standard-configuration)
  - [Adding entities](#adding-entities)
    - [Include](#include)
    - [Exclude](#exclude)
  - [Groups](#groups)
  - [Schedule discovery](#schedule-discovery)
  - [Customize](#customize)
    - [Options](#options-1)
    - [Actions](#actions)
    - [Numeric action variable](#numeric-action-variable)
    - [List action variable](#list-action-variable)
    - [Conditions](#conditions)
  - [Display options](#display-options)
  - [Tags](#tags)
- [Translations](#translations)
- [Tips & Tricks](#tips--tricks)
  - [Triggering multiple actions on a schedule](#triggering-multiple-actions-on-a-schedule)
  - [Customizing built-in actions](#customizing-built-in-actions)
- [Troubleshooting](#troubleshooting)
  - [Checking card version](#checking-card-version)
- [Say thank you](#say-thank-you)

## Introduction
Configuration, Automation and Dashboard YAML files to use a Zigbee Keypad. The Xfinity xhk1-ue was used for testing, but there shouldn't be a reason why this wouldn't work with other Zigbee (or zwave) keypads.

## Installation
<details>
<summary>click to show installation instructions </summary>
1. Download the latest release of `HA-Zigbee-Keypad-Xfinity-xhk1-ue` [here](https://github.com/LenirSantiago/HA-Zigbee-Keypad-Xfinity-xhk1-ue/tree/main) and place it into `./config`.
2. (optional) To enable users based on a schedule:
  2.1 make sure to install [here](https://github.com/nielsfaber/scheduler-component) 
  2.2 make sure to install [here](https://github.com/nielsfaber/scheduler-card) 
</details>
