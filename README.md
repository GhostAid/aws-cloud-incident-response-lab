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
- CloudTrail Analysis
- Threat Hunting
