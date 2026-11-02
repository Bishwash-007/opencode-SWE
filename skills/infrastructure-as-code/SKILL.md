# Infrastructure as Code

Define infrastructure through code, not manual console clicks. Every cloud resource must be declared in version-controlled configuration files.

## Overview

Infrastructure as Code (IaC) means your infrastructure is defined in code files (Terraform, CloudFormation, Pulumi, etc.) that are version-controlled, reviewed, and tested like application code. No manual console clicks.

## When to Use

- Provisioning new cloud resources
- Modifying existing infrastructure
- Replicating environments (staging, production, disaster recovery)
- Documenting infrastructure architecture

## Process

1. **Choose tool** — Terraform, AWS CloudFormation, Pulumi, or AWS CDK
2. **Define resources** — declare all infrastructure in code files
3. **Validate** — run `terraform validate` or equivalent
4. **Plan** — run `terraform plan` to preview changes
5. **Review** — have plan reviewed by team before apply
6. **Apply** — only with explicit user approval
7. **Commit** — infrastructure code committed alongside application code

## Terraform Best Practices

- **State management** — use remote state (S3 + DynamoDB, GCS, Azure Blob)
- **State locking** — prevent concurrent modifications
- **Workspaces** — separate environments (dev, staging, prod)
- **Modules** — reusable, tested infrastructure modules
- **Variable validation** — validate input variables
- **Output values** — expose important resource attributes
- **Dependencies** — explicit depends_on where needed

## Rationalizations & Rebuttals

| Excuse | Rebuttal |
|--------|----------|
| "I'll click it in the console" | Manual changes are untracked and unrepeatable. |
| "It's just one resource" | One manual change leads to configuration drift. |
| "State file is fine locally" | Local state is lost if your machine dies. Use remote state. |

## Red Flags

- Infrastructure created via console without code
- Terraform state stored locally
- No plan review before apply
- Hardcoded region or provider settings
- Missing state locking

## Verification

- `terraform validate` passes
- `terraform plan` reviewed before apply
- Infrastructure code committed to version control
- Remote state configured with locking
- Modules used for repeatable patterns