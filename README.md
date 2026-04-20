# GoodWe Home Assistant Dashboard

A Home Assistant YAML dashboard for GoodWe solar, battery, grid import/export, and house consumption monitoring.

## Features
- Battery State of Charge gauge
- Live PV, battery, import/export, and house load
- Daily and monthly energy summaries
- Daily and monthly built-in charts
- Built using native Home Assistant cards only

## Screenshot
![Dashboard screenshot](docs/screenshot.png)

## Requirements
This dashboard expects these entities to exist:

- sensor.goodwe_battery_state_of_charge
- sensor.goodwe_pv_power
- sensor.goodwe_pv1_power
- sensor.goodwe_pv2_power
- sensor.goodwe_house_consumption
- sensor.goodwe_battery_power
- sensor.goodwe_active_power_l1
- sensor.energy_buy
- sensor.energy_sell
- sensor.energy_battery_charge
- sensor.energy_battery_discharge
- sensor.house_consumption
- sensor.energy_buy_daily
- sensor.energy_buy_monthly
- sensor.energy_sell_daily
- sensor.energy_sell_monthly
- sensor.energy_battery_charge_daily
- sensor.energy_battery_charge_monthly
- sensor.energy_battery_discharge_daily
- sensor.energy_battery_discharge_monthly
- sensor.pv_energy_daily
- sensor.pv_energy_monthly
- sensor.pv1_energy_daily
- sensor.pv1_energy_monthly
- sensor.pv2_energy_daily
- sensor.pv2_energy_monthly
- sensor.house_consumption_daily
- sensor.house_consumption_monthly

## Installation

1. Copy `dashboards/goodwe_dashboard.yaml` into your Home Assistant config folder under `/config/dashboards/`.
2. Add the YAML snippet from `examples/configuration.yaml.snippet` into `configuration.yaml`.
3. Restart Home Assistant.
4. Open the dashboard from the sidebar.

## configuration.yaml snippet

```yaml
lovelace:
  mode: storage
  dashboards:
    goodwe-power:
      mode: yaml
      title: GoodWe Power
      icon: mdi:solar-power
      show_in_sidebar: true
      filename: dashboards/goodwe_dashboard.yaml
```

## Notes
- Uses built-in Home Assistant cards only.
- Assumes your energy helper sensors and utility meters already exist.
- You may need to rename entities if your GoodWe integration uses different entity IDs.

## Troubleshooting
- If the dashboard is blank, check the `filename` path.
- If you see YAML errors, verify spaces are used instead of tabs.
- If graphs fail, confirm the entities are producing long-term statistics.
