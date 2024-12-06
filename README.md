# Deposit Tracker - Ethereum

## Project Overview

The Deposit Tracker - Ethereum monitors and records Ethereum deposits on the Beacon Deposit Contract. It tracks deposits, stores data in a PostgreSQL database, sends alerts via Telegram, and configures Grafana dashboards for visualizing the data.

## Features

- Tracks Ethereum deposits on the Beacon Deposit Contract.
- Stores deposit data in a PostgreSQL database.
- Logs API status and database write operations.
- Sends Telegram alerts about new deposits.
- Configures a Grafana dashboard to display deposit volume graphs, fee statistics, and latest deposit data.

## File Structure

```bash
deposit-tracker-ethereum
|
|-- deposit_tracker
|   |-- main.py
|   |-- database.py
|   |-- tracker.py
|   |-- view_data.pgsql
|   |-- logs
|       |-- eth_deposit_tracker.log
|
|-- grafana
|   |-- dashboard_config.json
|
|-- telegram_alerts
|   |-- alert.py
|
|-- requirements.txt
