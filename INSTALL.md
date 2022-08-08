# Installation

* Install and configure [HACS](https://hacs.xyz/)

* Within HACS Frontend add the following repositories
  * [button-card](https://github.com/custom-cards/button-card)
  * [card-mod](https://github.com/thomasloven/lovelace-card-mod)
  * [layout-card](https://github.com/thomasloven/lovelace-layout-card)
  * [Swipe Card](https://github.com/bramkragten/swipe-card)

* Manually copy over these files from [matt8707/hass-config](https://github.com/matt8707/hass-config)
  * `ui-lovelace.yaml`
  * `button_card_templates` folder
  * `popup` folder
  * `themes.yaml`
  * `sidebar.yaml`

* In `configuration.yaml` add lines [[docs](https://www.home-assistant.io/lovelace/dashboards/)]

  ```yaml
  frontend: !include themes.yaml
  template: !include sidebar.yaml

  lovelace:
    mode: yaml #use ui-lovelace.yaml
    resources: #hacs
      - url: /hacsfiles/button-card/button-card.js
        type: module
      - url: /hacsfiles/lovelace-layout-card/layout-card.js
        type: module
      - url: /hacsfiles/swipe-card/swipe-card.js
        type: module
  ```

* In `secrets.yaml` add placeholders

  ```yaml
  youtube_token: abc
  apexcharts_tibber: abc
  apexcharts_influx: abc
  apexcharts_github: abc
  ```

* [Restart](https://my.home-assistant.io/redirect/server_controls/) Home Assistant

* **Select [tablet theme](https://my.home-assistant.io/redirect/profile/) ← DON'T SKIP THIS STEP!**

Then add your entities, [browser_mod](https://github.com/thomasloven/hass-browser_mod) for popups etc...
