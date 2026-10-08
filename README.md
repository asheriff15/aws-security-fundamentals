# AWS Security Fundamentals

![Platform](https://img.shields.io/badge/Platform-AWS-FF9900?logo=amazonaws&logoColor=white)
![Topics](https://img.shields.io/badge/Topics-IAM%20%7C%20Security%20Groups%20%7C%20NACLs-blue)
![Status](https://img.shields.io/badge/Status-Complete-brightgreen)

Hands-on AWS labs covering the two layers every cloud environment is secured with: **identity** (who can do what) and **network** (what traffic can reach what). Each lab follows the same pattern — configure a control, then **test it by trying something that should fail**.

| # | Lab | Layer | What it proves |
|---|---|---|---|
| 01 | [IAM Users](01-iam-users/) | Identity | A read-only user can view resources but is denied `iam:CreateUser` |
| 02 | [IAM Groups](02-iam-groups/) | Identity | Adding the same user to an admin group grants the permission it was missing |
| 03 | [Security Groups](03-security-groups/) | Network (instance) | Removing the HTTP rule takes a live web server offline; restoring it brings it back |
| 04 | [Network ACLs](04-network-acls/) | Network (subnet) | A subnet-level NACL blocks traffic even when the security group allows it |

---

## Security Groups vs. Network ACLs

The most common interview question these labs answer:

| | Security Group | Network ACL |
|---|---|---|
| Applies to | Instance (ENI) | Entire subnet |
| State | **Stateful** — return traffic is automatically allowed | **Stateless** — return traffic needs its own rule |
| Rules | Allow only | Allow **and** deny |
| Evaluation | All rules evaluated together | Lowest rule number first; first match wins |
| Default (custom) | Deny all inbound, allow all outbound | Custom NACL denies everything until you add rules |

---

## Tools & Technologies

AWS IAM · Amazon EC2 · Amazon VPC · Security Groups · Network ACLs · Route Tables · Apache (`httpd`) on Amazon Linux 2023

> Completed as part of coursework; write-ups and analysis are my own. Screenshots are redacted to remove the AWS account ID, IP addresses and sign-in URLs.

---

More of my projects and write-ups: **[asheriff15.github.io](https://asheriff15.github.io)**
