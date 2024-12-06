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


2. Set Up a Virtual Environment
bash
Copy code
python -m venv venv
venv\Scripts\activate
3. Install Dependencies
bash
Copy code
pip install -r requirements.txt
4. Configure Environment Variables
Create a .env file in the root directory with the following variables:

env
Copy code
ALCHEMY_API_KEY=your_alchemy_api_key
DATABASE_URL=your_postgresql_database_url
TELEGRAM_BOT_TOKEN=your_telegram_bot_token
TELEGRAM_RECIPIENT_IDS=comma_separated_recipient_ids
DEPOSIT_THRESHOLD=your_deposit_threshold  # Optional: Notify deposits above a specific amount
ALCHEMY_API_KEY: Get your Alchemy API key for Ethereum at Alchemy Dashboard.
DATABASE_URL: PostgreSQL connection URL in the format postgresql+psycopg2://postgres:<your_user_name>@localhost/deposits.
TELEGRAM_BOT_TOKEN: Create a Telegram bot and get the token using BotFather.
TELEGRAM_RECIPIENT_IDS: Comma-separated list of Telegram user IDs to receive alerts. Use userinfobot in Telegram to get user IDs.
DEPOSIT_THRESHOLD: Optional. Set a deposit amount threshold to receive alerts for large transactions only.
5. Set Up PostgreSQL Database
Download PostgreSQL from PostgreSQL Downloads.
The database schema will be created automatically when you run main.py.
6. Configure Grafana
Download Grafana from Grafana Downloads.
Access Grafana at http://localhost:3000.
Import the Grafana configuration JSON file located at grafana/dashboard_config.json to set up the dashboards.
Customize the panels to include metrics such as deposit count, average fees, and volume trends.
7. Run the Application
bash
Copy code
python deposit_tracker/main.py
Alerts and Monitoring
Telegram Alerts: Notifications are sent for each deposit or when deposits exceed a defined threshold.
Grafana Dashboards: Visualize key metrics such as:
Deposit volume over time.
Fee distribution and trends.
Real-time deposit logs.
Log Management: All operations, errors, and API statuses are logged in logs/eth_deposit_tracker.log.
Usage
View deposit data by executing queries from view_data.pgsql.
Access real-time visualizations and statistics on the Grafana dashboard.
Manage alert settings, thresholds, and recipients through the .env configuration.
Future Enhancements
Integration with additional Ethereum networks (e.g., Layer 2 solutions).
Automated scaling for handling high transaction volumes.
Advanced analytics for deposit patterns and predictive insights.
Multi-language support for alerts and dashboards.
Contributing
Contributions are welcome! Fork the repository and submit a pull request with your changes.

Copy code





