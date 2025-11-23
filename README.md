# Starting-with-N8n
Creating Projects with n8n

📘 Description

This project demonstrates how to build a simple yet powerful automation pipeline using n8n.
The workflow:

Runs weekly using a Schedule Trigger

Fetches solar flare data from NASA’s DONKI API

Filters solar flares based on their classType (A, B, C, M, X)

Uses an IF node to separate high-intensity (X-class) and lower-intensity flares

Sends categorized results to Postbin for visualization

It showcases the use of:

Scheduling triggers

API integration

Conditional branching

Expression handling

External data logging

This is a great introductory workflow for learning n8n automation + APIs + logic building.

🛠️ Tools / Technologies Used
🔹 n8n Automation Tool

Used for workflow orchestration, triggers, API calls, and logic flow.

🔹 NASA DONKI API

Provides real-time Solar Flare data for the past 30 days.
We use get:donkiSolarFlare.

🔹 Postbin

Used as a temporary data receiver to log messages based on classification.

🔹 Expressions in n8n

Used for:

Dynamic date calculation → {{ $today.minus(7, 'days') }}

Creating dynamic Postbin messages

Accessing JSON values

Filtering records

🔹 Schedule Trigger

Runs the workflow automatically every Monday at 9:00 AM.

📂 Workflow Structure

Here’s the workflow diagram used in this project (based on your screenshot):

📜 Workflow Steps
1. Schedule Trigger

Trigger type: Weekly

Day: Monday

Time: 09:00 AM

Fires weekly to fetch the latest solar flare data.

2. NASA DONKI Solar Flare Node

Operation: Get a DONKI solar flare

Credentials: NASA API key (generated from NASA APIs portal)

Additional field: Start date

Expression used:

{{ $today.minus(7, 'days') }}


Fetches only the last 7 days of solar flare activity.

3. IF Node – Classification Logic

Checks the value of:

classType


Condition:

String Contains → "X"

Purpose:

TRUE branch → High-intensity flares (X-class)

FALSE branch → Low/medium flares (A/B/C/M class)

4. Postbin – True Branch Output

Sends this message:

There was a solar flare of class {{$json["classType"]}}

5. Postbin – False Branch Output

Same structure, used for non-X class flares.

6. Execution & Testing

Click Execute Workflow

Verify output in Postbin URL

After validation, turn the workflow Active
→ It now runs weekly without manual intervention.

📊 Inferences / Key Learnings

How to use Scheduled Triggering in n8n

How to authenticate and call external APIs

How to use Expressions for dynamic date handling

How to implement logic branches using IF node

How to route different results to different outputs

How to log results externally via Postbin

Understanding solar flare classifications (A, B, C, M, X)

📈 Possible Extensions

You can extend this workflow to make it more powerful:

Send email/SMS alerts for X-class events

Store results in Airtable / Google Sheets / Notion

Use Telegram/Slack bots for live notifications

Create a dashboard using n8n + Supabase / MongoDB

Log flare events with timestamps for long-term analysis

📜 License

This project is intended for educational and demonstration purposes.
