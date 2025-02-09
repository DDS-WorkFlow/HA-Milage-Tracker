# Mileage Tracker for Home Assistant

A custom integration that automatically logs mileage by detecting Wi-Fi SSID changes through the Home Assistant Companion App.

## Features

- Wi-Fi SSID classification (Home, Work, Temporary Home, Ignore)
- Distance calculation via Google Distance Matrix (with caching)
- Flight vs. Drive prompts for long distances
- Manual trip service for overrides
- Actionable notifications
- Persists data in `.storage/mileage_tracker_data`

## Installation (HACS - Custom Repository)
1. Go to Home Assistant → HACS → Integrations → (3 dots) → Custom repositories.
2. Add this repository URL, select "Integration".
3. Search "Mileage Tracker" in HACS → Integrations, and install.
4. Restart Home Assistant.
5. Go to Settings → Devices & Services → + Add Integration → pick "Mileage Tracker".

## Manual Installation
1. Copy the `custom_components/mileage_tracker` folder into your `config/custom_components/`.
2. Restart Home Assistant.
3. Add the integration in HA.

## Usage
- Ensure you have the Companion App with Wi-Fi SSID sensor enabled.
- Configure the integration with your Google Distance Matrix API key, daily call limit, flight threshold.
- Classification prompts appear when connecting to new SSIDs.
- Trips are auto-logged when going from one classified SSID to another.
- Use the `mileage_tracker.add_manual_trip` service for missed trips or overrides.
