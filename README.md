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
CloudTrail logs were reviewed to identify suspicious activity and reconstruct an attack timeline.

## Findings
- Reconnaissance activity detected
- IAM enumeration attempts observed
- Privilege escalation attempt blocked by IAM policies

## Skills Demonstrated
- Cloud Security
- Incident Response
- AWS IAM

- ## Architecture Diagram

![Architecture Diagram](https://github.com/GhostAid/aws-cloud-incident-response-lab/blob/main/architecture-diagram.PNG)

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
- CloudTrail Analysis
- Threat Hunting
