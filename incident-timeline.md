# Incident Timeline

## Summary

A simulated compromised IAM user (`victim-user`) was used to perform reconnaissance and unauthorized IAM actions within an AWS environment.

| Time (UTC) | Event Name | Username | Source IP | Result | Analysis |
|------------|------------|-----------|-----------|----------|----------|
| 21:19 | GetCallerIdentity | victim-user | 102.89.34.71 | AccessDenied | Attempted to verify AWS account identity using compromised credentials. |
| 21:20 | ListBuckets | victim-user | 102.89.34.71 | AccessDenied | Attempted enumeration of S3 buckets within the AWS account. |
| 21:21 | ListBuckets | victim-user | 102.89.34.71 | AccessDenied | Repeated S3 enumeration attempt, indicating continued reconnaissance activity. |
| 21:34 | CreateUser | victim-user | 102.89.34.71 | AccessDenied | Unauthorized attempt to create a new IAM user, potentially indicating privilege escalation efforts. |
| 21:39 | ListUsers | victim-user | 102.89.34.71 | AccessDenied | Attempted enumeration of IAM users to identify privileged accounts and expand access. |

## Findings

- All activity originated from the same source IP address.
- The account performed cloud resource reconnaissance.
- Multiple IAM-related actions were denied.
- Activity resembles an attacker attempting discovery and privilege escalation.

## Containment Actions

- Reviewed CloudTrail logs for suspicious activity.
- Verified IAM permissions assigned to `victim-user`.
- Confirmed unauthorized actions were blocked by AWS IAM policies.
- Recommended credential rotation and continued monitoring.
