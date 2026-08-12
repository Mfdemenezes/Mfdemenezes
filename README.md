# Marcelo Ferreira de Menezes

**Cloud infrastructure — AWS, Terraform, Docker.** Animal Science graduate who spent
years running farm operations, now building the infrastructure side of software.

The through line is the same work in a different domain: measure what is happening,
remove what is wasteful, make the result repeatable. It used to be herd nutrition and
production planning. Now it is VPCs, pipelines and cost per month.

Everything below runs, or ran, for real — a self-hosted stack on a free-tier ARM box,
automations a therapy practice depends on, infrastructure defined in Terraform and
deployed through CI. Not tutorials followed to the end.

**Currently:** AWS Certified Cloud Practitioner, studying for Solutions Architect – Associate.
Open to cloud/DevOps roles, remote or relocation.

---

## Selected work

| Repository | What it demonstrates |
|---|---|
| **[aws-rds-terraform](https://github.com/Mfdemenezes/aws-rds-terraform)** | A database that is private by construction: no public endpoint, credentials generated and rotated by RDS in Secrets Manager, ingress by security group reference, Multi-AZ. Documented as a before/after of 12 security fixes to the version I first wrote — including the committed password. |
| **[aws-alb-private-ec2](https://github.com/Mfdemenezes/aws-alb-private-ec2)** | VPC with public and private subnets across two AZs, internet-facing ALB, EC2 with no public address administered through SSM. The README states the cost and the gaps rather than hiding them. |
| **[aws-static-site-cdn](https://github.com/Mfdemenezes/aws-static-site-cdn)** | S3 + CloudFront + ACM with a GitHub Actions pipeline that plans on every push and invalidates the CDN cache on release. |
| **[aws-terraform-modules](https://github.com/Mfdemenezes/aws-terraform-modules)** | Reusable EC2, VPC, security group and S3 modules — encrypted EBS, SSM Session Manager instead of SSH, no key pairs to distribute. |
| **[jarvis](https://github.com/Mfdemenezes/jarvis)** | Personal AI assistant on Oracle Cloud free tier: FastAPI, PostgreSQL with pgvector, Redis, NGINX, reachable from a PWA and from WhatsApp. The model is a tool-use agent that chains up to six calls before answering. |
| **[n8n-automations](https://github.com/Mfdemenezes/n8n-automations)** | Automations in production: AI agents over Telegram, scheduled AWS cost reporting into PostgreSQL, form intake pipelines into Sheets, Drive and Gmail. |

## How the CI works

Every Terraform repository authenticates to AWS through **OIDC** — GitHub assumes a role
with a short-lived token and no access keys are stored as secrets. The role is read-only
plus state access, so pipelines can validate and plan but cannot provision anything.
Applying is a deliberate, manual dispatch.

The trust policy is pinned to immutable repository IDs rather than names, because
GitHub embeds those IDs in the OIDC subject once a repository is renamed.

## Tools

`AWS` `Terraform` `Docker` `Docker Compose` `GitHub Actions` `Linux` `Python`
`PostgreSQL` `Redis` `NGINX` `n8n` `Oracle Cloud` `Kubernetes (learning)`

## Certifications

- AWS Certified Cloud Practitioner
- AWS Certified Solutions Architect – Associate *(in progress)*

## Contact

[LinkedIn](https://www.linkedin.com/in/marcelomenezzes/) · mfdemenezes@gmail.com
