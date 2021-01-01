# aws_ses_domain_mail_from

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "aws_ses_domain_mail_from" {
  source = "./modules/aws/r/aws_ses_domain_mail_from"

  # behavior_on_mx_failure - (optional) is a type of string
  behavior_on_mx_failure = null
  # domain - (required) is a type of string
  domain = null
  # mail_from_domain - (required) is a type of string
  mail_from_domain = null
}
```

[top](#index)

### Variables

```hcl
variable "behavior_on_mx_failure" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(required)"
  type        = string
}

variable "mail_from_domain" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_ses_domain_mail_from" "this" {
  behavior_on_mx_failure = var.behavior_on_mx_failure
  domain                 = var.domain
  mail_from_domain       = var.mail_from_domain
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_ses_domain_mail_from.this.id
}

output "this" {
  value = aws_ses_domain_mail_from.this
}
```

[top](#index)