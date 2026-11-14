# Detection Engineering and Validation Plan

**Status: Planned, not implemented.** This document defines tests to perform in the authorised Wazuh lab. Do not treat these scenarios as completed detections.

## Candidate use cases

| Use case | Proposed telemetry | Detection intent | Test status |
| --- | --- | --- | --- |
| Repeated failed authentications | OS authentication events ingested by Wazuh | Detect an unusual burst of failures, controlling for benign mistakes | Not tested |
| New local privileged account | Relevant macOS/Linux account-management audit events | Identify account creation or privilege changes | Not tested |
| Security agent stopped | Agent status and server-side health events | Identify gaps in endpoint visibility | Not tested |
| Unexpected persistence change | Relevant OS audit/file monitoring events | Flag suspicious persistence-related changes | Not tested |

Availability of each telemetry field must be confirmed in the user's actual macOS setup before writing a rule.

## Validation requirements for each custom detection

1. Document the log source, schema, and prerequisites.
2. Establish a benign baseline in the isolated lab.
3. Generate a safe, authorised positive test case.
4. Collect anonymised events and exact rule output.
5. Include at least one negative/benign test to estimate false positives.
6. Document expected vs actual result, rule version, Wazuh version, and limitations.
7. Map to specific MITRE ATT&CK technique IDs only when technically justified.

## Suggested metrics

- Test cases triggered / total positive test cases
- Benign test cases incorrectly alerted / total benign test cases
- Detection latency, if timestamps can be reliably correlated
- Analyst time to triage, if measured

Avoid claiming production precision/recall from a handful of synthetic test cases.

## Next experiment

Choose one log source that is already visible in the Wazuh dashboard. Capture a redacted sample event and identify a benign and positive test before authoring a custom rule.
