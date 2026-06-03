# Bonus — Uptime Monitor Workflow
Author: Sawan Bhardwaj

## What it does
Pings saucedemo.com every 5 minutes and sends a Telegram 
alert if the site is down or returns an error.

## Nodes

**Node 1 — Schedule Trigger**
Fires every 5 minutes automatically. The alarm clock 
of the workflow.

**Node 2 — HTTP Request (Ping)**
Visits saucedemo.com like a browser would. 
Continue On Fail is enabled so if the site is dead, 
the error is passed forward instead of crashing the workflow.

**Node 3 — IF Node**
Checks if Node 2 returned an error.
- YES (site down) → triggers Telegram alert
- NO (site healthy) → workflow ends silently

**Node 4 — Telegram Alert**
Only fires when site is down. Sends message with 
error details and timestamp to Telegram group.

## Logic in one line
Every 5 min → ping site → if error → alert on Telegram.

## Screenshot
![bonus_task_screenshot](image.png)