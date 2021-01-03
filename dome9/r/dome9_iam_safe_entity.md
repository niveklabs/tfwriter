# dome9_iam_safe_entity

[back](../dome9.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    dome9 = ">= 1.20.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "dome9_iam_safe_entity" {
  source = "./modules/dome9/r/dome9_iam_safe_entity"

  # aws_cloud_account_id - (required) is a type of string
  aws_cloud_account_id = null
  # dome9_users_id_to_protect - (optional) is a type of list of string
  dome9_users_id_to_protect = []
  # entity_name - (required) is a type of string
  entity_name = null
  # entity_type - (required) is a type of string
  entity_type = null
  # protection_mode - (required) is a type of string
  protection_mode = null
}
```

[top](#index)

### Variables

```terraform
variable "aws_cloud_account_id" {
  description = "(required)"
  type        = string
}

variable "dome9_users_id_to_protect" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "entity_name" {
  description = "(required)"
  type        = string
}

variable "entity_type" {
  description = "(required)"
  type        = string
}

variable "protection_mode" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "dome9_iam_safe_entity" "this" {
  aws_cloud_account_id      = var.aws_cloud_account_id
  dome9_users_id_to_protect = var.dome9_users_id_to_protect
  entity_name               = var.entity_name
  entity_type               = var.entity_type
  protection_mode           = var.protection_mode
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = dome9_iam_safe_entity.this.arn
}

output "attached_dome9_users" {
  description = "returns a list of string"
  value       = dome9_iam_safe_entity.this.attached_dome9_users
}

output "exists_in_aws" {
  description = "returns a bool"
  value       = dome9_iam_safe_entity.this.exists_in_aws
}

output "id" {
  description = "returns a string"
  value       = dome9_iam_safe_entity.this.id
}

output "state" {
  description = "returns a string"
  value       = dome9_iam_safe_entity.this.state
}

output "this" {
  value = dome9_iam_safe_entity.this
}
```

[top](#index)