# IoT Diagnostic & Support Tooling

Internal diagnostic tool built for support and operations teams, 
providing real-time visibility into the full IoT command chain — 
from user intent in the mobile app down to individual connected devices.

## Context

Support teams lacked visibility into why a device was not responding 
to a user command. Diagnosing issues required manual cross-referencing 
across multiple internal systems, with no unified view of the command 
pipeline. Investigations were slow and error-prone.

## What it does

### Command chain tracing
For each device on a site, the tool displays the full command pipeline 
end-to-end:

- User intent (weekly schedule, manual control, quick mode, 
  absence detection) and target setpoint (comfort, eco, frost 
  protection, temperature, off)
- Order status at each layer: platform → gateway (4G) → 
  module (Zigbee) → device
- Visual warning when an inconsistency is detected at any layer, 
  with clear indication of where the chain breaks

### Configuration diagnostics
Surfaces configuration issues not visible in the CRM:

- Duplicate login detection in the database
- Missing email or undefined login
- Onboarding completion status
- Connection frequency
- Email history (welcome, activation code) with delivery status
- Self-service diagnostic results run by the user in the app, 
  with timestamps

### Remote command tools
Pre-configured commands for support teams to trigger gateway 
and module actions (re-pairing, reset) — scoped and locked 
to prevent unauthorized or dangerous operations.

## Access
The tool can be accessed via site ID, member ID, or email address. 
Authentication via internal login.

## Stack

- **Python** — backend, data queries, API calls
- **Internal APIs** — IoT platform, gateway communication layer
- **MySQL / BigQuery** — device state and configuration data
- **Vibe coding (AI-assisted)** — ergonomic frontend interface

## Impact

- Used daily by 12 support and operations team members
- Several diagnostic capabilities and corrective actions were 
  only available through this tool — not in the CRM or any 
  other internal system
- Eliminated escalation chains (N1 support → PM → engineering) 
  for a large class of issues: support agents can diagnose and 
  act autonomously
- Reduced diagnostic time from minutes to seconds per case
- Direct impact on customer satisfaction: issues resolved 
  immediately during the support call rather than after 
  multi-day escalation cycles

## Notes

Source code is proprietary and internal to Voltalis. 
This README documents the product scope and technical approach only.
