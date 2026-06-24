Incident Findings Report

Executive Summary

This project simulated a compromised AWS IAM user account (victim-user) and analyzed the resulting CloudTrail logs. The objective was to identify suspicious activity, reconstruct a timeline, and evaluate the effectiveness of AWS security controls.

Investigation Scope

The investigation focused on activity performed by the IAM user victim-user using AWS CLI commands that generated CloudTrail events.

Observed Events

* GetCallerIdentity
* ListBuckets
* ListUsers
* CreateUser

All observed events originated from the source IP address 102.89.34.71.

Key Findings

1. Credential Validation Activity

The GetCallerIdentity API call indicates that the user attempted to verify the validity of AWS credentials.

2. Resource Enumeration

The ListBuckets events suggest reconnaissance activity intended to identify available S3 resources within the AWS account.

3. IAM Enumeration

The ListUsers event indicates an attempt to discover IAM users and identify potentially privileged accounts.

4. Privilege Escalation Attempt

The CreateUser event represents an attempt to create a new IAM user. This behavior may indicate an effort to establish persistence or obtain elevated privileges.

5. Effective Security Controls

All observed actions resulted in AccessDenied responses. This demonstrates that IAM permissions successfully prevented unauthorized access and privilege escalation attempts.

Impact Assessment

No resources were modified or created during the simulation. The impact was limited because IAM policies restricted access to sensitive actions.

Containment Actions

* Reviewed CloudTrail logs.
* Investigated suspicious API calls.
* Verified IAM permissions assigned to the user.
* Confirmed that unauthorized actions were blocked.
* Recommended ongoing monitoring and credential rotation.

Conclusion

CloudTrail successfully captured the simulated attacker activity and enabled reconstruction of the attack timeline. The investigation demonstrated how AWS logging and IAM controls can be used to detect and prevent unauthorized actions.
