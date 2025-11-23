# NASA Solar Flare Automation using n8n
A simple yet powerful automation workflow built in n8n to fetch, classify, and log real-time solar flare activity using NASA’s DONKI API.

## Description
This project demonstrates how to build a complete automation pipeline using n8n.
The workflow runs weekly, fetches solar flare data, filters based on classType, branches using IF node, and logs results to Postbin.

## Tools / Technologies Used
- n8n Automation Tool
- NASA DONKI API
- Postbin
- Expressions in n8n
- Schedule Trigger

## Workflow Steps
1. Schedule Trigger
2. NASA DONKI Solar Flare Node
3. IF Node – Classification Logic
4. Postbin – TRUE Branch Output
5. Postbin – FALSE Branch Output
6. Execution & Testing

## Inferences / Key Learnings
- Scheduled Triggers
- API integrations
- Expressions
- Logic branching
- External logging

## Possible Extensions
- Alerts
- Storage in Google Sheets/Notion/Airtable
- Slack/Telegram notifications
- Dashboards

## License
For educational purposes.
