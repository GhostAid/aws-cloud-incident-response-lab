## Project Files

- [Incident Timeline](incident-timeline.md)
- [Findings Report](findings.md)
# AWS Cloud Incident Response Lab

## Overview
This project simulates a compromised IAM user in AWS and investigates the resulting CloudTrail logs.

## Technologies Used
- AWS IAM
- AWS CloudTrail
- Amazon S3
- AWS CLI

## Attack Simulation
- GetCallerIdentity
- ListBuckets
- ListUsers
- CreateUser

## Investigation

CloudTrail logs were reviewed to identify suspicious API activity and reconstruct an attack timeline.

The investigation correlated events using the IAM username and source IP address. The observed sequence included GetCallerIdentity, repeated ListBuckets requests, CreateUser, and ListUsers.

All observed requests returned AccessDenied, confirming that the IAM permissions assigned to victim-user prevented the simulated actions from succeeding.
## Findings

- Reconnaissance activity detected
- S3 resource enumeration attempts observed through ListBuckets
- IAM identity enumeration observed through ListUsers
- IAM account manipulation attempt observed through CreateUser
- All observed API requests returned AccessDenied
- No evidence of successful resource modification, account creation, or privilege escalation was identified

## MITRE ATT&CK Mapping

The observed activity was mapped to relevant MITRE ATT&CK techniques to provide a standardized view of the simulated behavior.

- ListBuckets — Cloud Storage Object Discovery (T1619)
- ListUsers — Account Discovery (T1087)
- CreateUser — Account Manipulation (T1098)

The mappings represent attempted activity observed in CloudTrail. They do not indicate successful execution because all recorded requests returned AccessDenied.

## Skills Demonstrated
- Cloud Security
- Incident Response
- AWS IAM
- AWS CloudTrail
- AWS CLI
- Threat Hunting
- Log Analysis
- Security Monitoring

- ## Architecture Diagram

![Architecture Diagram](https://github.com/GhostAid/aws-cloud-incident-response-lab/blob/main/architecture-diagram.PNG)
**Note:** The "Attacker / Tester" component represents a controlled simulation performed by the project author using AWS CLI and test credentials to generate CloudTrail events for incident response analysis.


## Lessons Learned

- AWS CloudTrail provides valuable visibility into account activity and API calls.
- Least-privilege IAM permissions help prevent unauthorized actions.
- Reconnaissance activities such as ListBuckets and ListUsers can indicate early stages of an attack.
- CloudTrail logs can be used to reconstruct an attack timeline during investigations.
- Proper logging and monitoring are essential for cloud incident response.
## Future Improvements

- Develop a Python-based CloudTrail log parser.
- Create automated alerts using Amazon CloudWatch.
- Integrate CloudTrail logs into Wazuh for centralized monitoring.
- Build custom detection rules for IAM privilege escalation attempts.
- Implement automated response actions using AWS Lambda.
- Expand the lab to include multiple AWS accounts and cross-account monitoring.
  
