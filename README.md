# Zigbee Keypad Control for Home Assistant <!-- omit in TOC -->
![GitHub last commit](https://img.shields.io/github/last-commit/LenirSantiago/HA-Zigbee-Keypad-Xfinity-xhk1-ue)

- [Introduction](#introduction)
- [Installation](#installation)
- [Updating](#updating)
- [Configuration](#configuration)
- [Usage](#usage)
- [Troubleshooting](#troubleshooting)
  - [Checking card version](#checking-card-version)
- [Say thank you](#say-thank-you)

## Introduction
This project helps use Zigbee Keypad in [`Home Assistant`](https://www.home-assistant.io/) using automations, scripts and dashboard YAML files.

By default it creates two types of users: 
- User Codes: The user names and codes are configurable as well as can be enabled/disabled manually or set by a schedule. 
    - By default, (4) users are created but more can be added in the YAML file.
    - By default, user names are 10-characters long, but the character length can be changed accodingly in the YAML file.
- One-Time Codes: These codes work only once before they have to be reset (assigned)
    - By default, (2) one-time codes are created but more can be added in the YAML file.

| NOTE: the all codes are 4-digit long, but digit length can be changed to support the keypad model in use.

The project uses HA [`events`](https://www.home-assistant.io/docs/configuration/events/) to trigger the automations. The automations authenticate the users and then trigger action scripts to do whatever you wish. For example, toggle a switch, open a door, etc.

| NOTE: The Xfinity XHK1-UE was used for testing, but there shouldn't be a reason why this wouldn't work with other Zigbee (or zwave) keypads.

## Installation
1. Install the [`Home Assistant ZHA (Zigbee Home Automation) integration`](https://www.home-assistant.io/integrations/zha/)
2. Make sure you Zigbee Keypad is discovered properly
2. Copy the contents of [`./blueprints/keypad`](https://github.com/LenirSantiago/HA-Zigbee-Keypad-Xfinity-xhk1-ue/tree/main) and place it into `./config/blueprints/keypad`.  
3. Copy the contents of  [`./packages/keypad`](https://github.com/LenirSantiago/HA-Zigbee-Keypad-Xfinity-xhk1-ue/tree/main) and place it into `./config/packages/keypad`.  
4. Copy the following into `./config/configuration.yaml`:
    ```bash
    homeassistant:  
        packages: !include_dir_named packages
    ```
5. Install HACS Frontend [`lovelace-mushroom`](https://github.com/piitaya/lovelace-mushroom)
6. Install HACS Frontend [`lovelace-mushroom-themes`](https://github.com/piitaya/lovelace-mushroom-themes)
7. Install HACS Frontend [`lovelave-card-mod`](https://github.com/thomasloven/lovelace-card-mod)
8. (optional) To enable users based on a schedule:  
    1. Install HACS Integration [`scheduler-component`](https://github.com/nielsfaber/scheduler-component)  
    2. Install HACS Frontend [`scheduler-card`](https://github.com/nielsfaber/scheduler-card)
9. Create a dashboard or a view for the keypad
10. Copy the contents of `./dashboard.yaml` into your dashboard/view.
10. Reload Home Assistant

## Configuration
- Import automations from the blueprints provided
- Edit the automations to trigger the corresponding action or scripts that you wish. Some examples are provided in this project.
- Go to your keypad dashboard/view. Here you can:
    - enable/disable the users by pressing on the corresponding button. 
        - One-Time codes are considered disabled when set to `0000`
    - Set user names and codes
    - If using a schedule:
      - Add a schedule for each user code and one-time code:  
          <img src="https://github.com/LenirSantiago/HA-Zigbee-Keypad/blob/main/images/configure_entity.png" width="300"/>  
          - Select Group Input Button  
          - Select the Keypad Button User entity  
          - Select either "Action Press" or "Make Scheme" (Preferrred)  
          <img src="https://github.com/LenirSantiago/HA-Zigbee-Keypad/blob/main/images/configure_time.png" width="300" />

          - Select `Press` action during the timeslots where the user will be active/enabled.  
          - NOTE: Users will be disabled/inactive during empty timeslots.  
          <img src="https://github.com/LenirSantiago/HA-Zigbee-Keypad/blob/main/images/configure_options.png" width="300" />

          - For each user schedule:
            - Name: Keypad User Slot 1, Tag: User
            - Name: Keypad User Slot 2, Tag: User
            - Name: Keypad User Slot 3, Tag: User
            - Name: Keypad User Slot 4, Tag: User
            - Name: Keypad One-Time Slot 1, Tag: Onetime
            - Name: Keypad One-Time Slot 2, Tag: Onetime
      - you can enable/disable the users' schedules.
      - Edit the users' schedules.

## Usage

If everything is configured properly, simply press a 4-digit code on the keypad.

For more advanced scheduling, please check https://github.com/nielsfaber/scheduler-card

## Troubleshooting

If you have an issue with this scheduler card, please report it [here](https://github.com/nielsfaber/scheduler-card/issues).

Also check https://github.com/nielsfaber/scheduler-card?tab=readme-ov-file#troubleshooting


---


## Say thank you
If you want to make donation as appreciation of my work, you can do so via PayPal (preferred) or buy me a coffee. Thank you!

<a href="https://www.paypal.com/donate/?hosted_button_id=DR8A2V27EZYVN" target="_blank"><img src="https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif" width="150" /></a>
<a href="https://www.buymeacoffee.com/lenirsantiago" target="_blank"><img src="https://www.buymeacoffee.com/assets/img/custom_images/orange_img.png"></a>
