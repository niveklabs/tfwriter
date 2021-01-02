# aws_securityhub_member

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_securityhub_member" {
  source = "./modules/aws/r/aws_securityhub_member"

  # account_id - (required) is a type of string
  account_id = null
  # email - (required) is a type of string
  email = null
  # invite - (optional) is a type of bool
  invite = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(required)"
  type        = string
}

variable "email" {
  description = "(required)"
  type        = string
}

variable "invite" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_securityhub_member" "this" {
  account_id = var.account_id
  email      = var.email
  invite     = var.invite
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_securityhub_member.this.id
}

output "master_id" {
  description = "returns a string"
  value       = aws_securityhub_member.this.master_id
}

output "member_status" {
  description = "returns a string"
  value       = aws_securityhub_member.this.member_status
}

output "this" {
  value = aws_securityhub_member.this
}
```

[top](#index)