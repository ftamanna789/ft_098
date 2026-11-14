# Architecture and Evidence Register

## Documented baseline

- macOS Sequoia on MacBook Air M3
- Local Wazuh services deployed using Docker / OrbStack
- Wazuh macOS agent v4.14.5
- Local vulnerability findings and security configuration assessment examined through Wazuh

These components are reported in the [source lab](https://github.com/ftamanna789/mini-soc-alert-triage-lab-mac). Exact network topology, service versions other than the agent, and event transport should be verified against the active deployment before publishing an architecture diagram.

## Evidence register

| ID | Evidence requested | Source | Status |
| --- | --- | --- | --- |
| E01 | Sanitised Wazuh dashboard overview | Original lab / new safe capture | To select |
| E02 | Agent connected and sending telemetry | Local lab | To collect/verify |
| E03 | Vulnerability counts before updates | Original lab | To cross-reference |
| E04 | Vulnerability counts after updates | Original lab | To cross-reference |
| E05 | Redacted event showing investigation fields | Authorised lab | To collect |
| E06 | Positive and benign detection-rule tests | Future lab experiment | Not performed |

## Diagram checklist

When verified, document: monitored endpoint, agent, transport path, Wazuh manager, indexer and dashboard. Do not invent addresses or imply separate hosts if components share the same computer.

## Safe publication

Avoid raw credentials, API keys, hostname, private/public IP addresses, user identity, serial numbers and confidential payloads. Replace sensitive details with clearly-labelled placeholders without changing event interpretation.
