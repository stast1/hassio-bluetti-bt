# hassio-bluetti-bt (Version 0.1.5-fork.1)
[![hacs_badge](https://img.shields.io/badge/HACS-Default-41BDF5.svg)](https://github.com/hacs/integration)
[![Validate with hassfest](https://github.com/Patrick762/hassio-bluetti-bt/actions/workflows/hassfest_validation.yml/badge.svg)](https://github.com/Patrick762/hassio-bluetti-bt/actions/workflows/hassfest_validation.yml)
[![HACS Action](https://github.com/Patrick762/hassio-bluetti-bt/actions/workflows/HACS.yml/badge.svg)](https://github.com/Patrick762/hassio-bluetti-bt/actions/workflows/HACS.yml)

Bluetti Integration for Home Assistant

## Disclaimer
This integration is provided without any warranty or support by Bluetti (unfortunately). I do not take responsibility for any problems it may cause in all cases. Use it at your own risk.

## Installation
To install this integration, you first need [HACS](https://hacs.xyz/) installed.
After the installation, you can use this button to install the integration:

[![Open your Home Assistant instance and open a repository inside the Home Assistant Community Store.](https://my.home-assistant.io/badges/hacs_repository.svg)](https://my.home-assistant.io/redirect/hacs_repository/?owner=Patrick762&repository=hassio-bluetti-bt&category=integration)

### Supported devices:

- AC60
- AC70 (basic data)
- AC70P (untested)
- AC180 (basic data)
- AC180P (tested)
- AC200L (untested)
- AC200M
- AC300 (tested)
- AC500 (tested)
- EB3A
- EP500
- EP500P
- EP600 (tested)
- EP760 (basic data)
- EP800 (basic data)

### Available controls:
If enabled in the Integration options (you need to reload the integration if you change this option):
AC and DC outputs

## Reliable BLE connection

Home Assistant emits a warning if `BleakClient.connect()` is called directly:

"BleakClient.connect() called without bleak-retry-connector. For reliable connection establishment, use bleak_retry_connector.establish_connection()."

This integration now uses `bleak-retry-connector` to establish BLE connections with retry and service cache. This reduces transient connection failures and improves stability.

## Reloading the integration

The integration now supports reloading from the Home Assistant UI. This allows you to:

- Apply configuration changes without restarting Home Assistant
- Reconnect to the device if connection issues occur
- Update the integration after changing options

To reload the integration:

1. Go to **Settings** → **Devices & Services**
2. Find the **Bluetti BT** integration
3. Click the three dots menu (⋮)
4. Select **Reload**

The integration will cleanly disconnect from the device, unload all entities, and then reconnect with the current configuration.
