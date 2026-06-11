# AWS Cloud Security CTF – Chained Attack Walkthrough

This repository contains my writeup for an AWS-focused Capture The Flag challenge completed during a cloud security bootcamp in 2026.

The challenge explores how multiple low and medium severity issues can be chained together to achieve a full compromise of a cloud environment. Rather than focusing on a single vulnerability, it demonstrates the importance of understanding relationships between AWS services and IAM permissions.

----

## Topics Covered

- S3 bucket enumeration

- Bucket policy misconfigurations

- Server-Side Request Forgery (SSRF)

- EC2 Instance Metadata Service (IMDSv1)

- IAM role credential theft

- AWS Lambda enumeration and abuse

- Secrets Manager credential extraction

- IAM policy version rollback (Shadow Admin)

- Privilege escalation

- Access to restricted resources
 
----

## Attack Flow
```
Public S3 Enumeration
        ↓
Private Bucket Access
        ↓
Infrastructure Discovery
        ↓
SSRF → EC2 Metadata
        ↓
IAM Role Credentials
        ↓
Lambda Enumeration
        ↓
Code Injection
        ↓
Secrets Extraction
        ↓
Developer Credentials
        ↓
Policy Version Rollback
        ↓
Privilege Escalation
        ↓
Restricted Bucket Access
```
---

## Key Takeaways

The challenge highlights several common cloud security pitfalls:

- Overly permissive S3 access

- Exposed metadata services through SSRF

- Unsafe execution of user-controlled input

- Poor secrets management

- Excessive IAM permissions

- Risks associated with retained policy versions

It also reinforces how seemingly isolated misconfigurations can be combined into a complete attack path.

-----

Repository Contents: 

- Detailed exploitation steps

- Commands used during enumeration and exploitation

----

Note

This writeup documents a controlled CTF environment created for educational purposes. The techniques discussed are intended for authorized security testing, training, and research only.
