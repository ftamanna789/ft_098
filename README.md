# Enterprise SOC Detection & Incident Response Lab

**Portfolio focus:** SOC alert triage · Endpoint security · Vulnerability management · Incident response · MITRE ATT&CK

> **Status:** Portfolio documentation in progress. This repository is being developed from an existing, documented Wazuh lab. The measurements below were recorded in that original lab; they are **not** results from a newly deployed enterprise environment. Custom detections and attack simulations are planned and must be validated before being marked complete.

## Project objective

Build a transparent, reproducible SOC case-study portfolio demonstrating how to collect endpoint telemetry, triage security findings, validate remediation, and document incidents. The lab is for authorised defensive testing only.

## Existing lab baseline (documented)

| Component | Environment |
| --- | --- |
| Host | MacBook Air (Apple M3, 16 GB) |
| Operating system | macOS Sequoia |
| SIEM / XDR | Wazuh |
| Agent | Wazuh agent v4.14.5 |
| Deployment | Local Docker / OrbStack lab |
| Other tooling | macOS Terminal, Wireshark |

Source: [Mini SOC Alert Triage Lab on Mac Using Wazuh](https://github.com/ftamanna789/mini-soc-alert-triage-lab-mac).

### Recorded remediation results

| Severity | Before | After | Reduction |
| --- | ---: | ---: | ---: |
| Critical | 10 | 7 | 3 |
| High | 61 | 51 | 10 |
| Medium | 165 | 123 | 42 |
| Low | 21 | 19 | 2 |
| **Total** | **257** | **200** | **57 (22.2%)** |

The existing project also reports security configuration assessment results: **37 passed**, **20 failed**, **2 not applicable**, with a reported **64% score**. These are lab observations, not an independently verified enterprise deployment.

## SOC investigation workflow

1. **Detect:** identify the alert, event time, asset, log source, and rule ID.
2. **Triage:** validate context, severity, potential false positives, and business impact.
3. **Investigate:** collect relevant endpoint/network logs and construct an evidence-based timeline.
4. **Map:** reference relevant MITRE ATT&CK techniques only when supported by evidence.
5. **Respond:** recommend containment/remediation; perform changes only in authorised lab systems.
6. **Validate:** check whether follow-up telemetry supports successful remediation.
7. **Report:** document findings, limitations, and next actions.

See [Incident investigation template](docs/incident-investigation-template.md) and [Detection engineering plan](docs/detection-engineering-plan.md).

## Repository structure

- `docs/` — reusable investigation workflow, detection plan, and architecture notes
- `detections/` — future tested detection rules with benign/positive test cases
- `investigations/` — future lab case studies with evidence references
- `evidence/` — redacted screenshots or safe synthetic logs

Empty planned folders will be introduced as actual files and supporting evidence become available.

## Roadmap

- [x] Establish a documented Wazuh lab baseline (in original repository)
- [x] Record vulnerability remediation and configuration-assessment measurements (in original repository)
- [x] Create this portfolio overview and investigation template
- [ ] Add a validated architecture diagram for the actual setup
- [ ] Produce one fully evidenced alert investigation
- [ ] Develop and test custom Wazuh detection rules
- [ ] Map confirmed detections to specific MITRE ATT&CK techniques
- [ ] Add reproducible, authorised attack simulations with safe sample logs
- [ ] Document false-positive checks and detection limitations

## Evidence and ethics

Use authorised lab environments only. Redact usernames, public IP addresses, hostnames, serial numbers, credentials and tokens; never publish real sensitive PCAPs, customer data or secrets. Distinguish actual findings from synthetic exercises and planned work.

## Career relevance

Aimed at SOC Analyst, Security Operations, Threat Detection and junior Detection Engineering roles. This work illustrates defensive lab practice; it does **not** claim production incident-response experience.
