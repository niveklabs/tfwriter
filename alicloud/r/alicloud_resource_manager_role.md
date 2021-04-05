# alicloud_resource_manager_role

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_resource_manager_role" {
  source = "./modules/alicloud/r/alicloud_resource_manager_role"

  # assume_role_policy_document - (required) is a type of string
  assume_role_policy_document = null
  # description - (optional) is a type of string
  description = null
  # max_session_duration - (optional) is a type of number
  max_session_duration = null
  # role_name - (required) is a type of string
  role_name = null
}
```

[top](#index)

### Variables

```terraform
variable "assume_role_policy_document" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_session_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "role_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_resource_manager_role" "this" {
  assume_role_policy_document = var.assume_role_policy_document
  description                 = var.description
  max_session_duration        = var.max_session_duration
  role_name                   = var.role_name
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = alicloud_resource_manager_role.this.arn
}

output "create_date" {
  description = "returns a string"
  value       = alicloud_resource_manager_role.this.create_date
}

output "id" {
  description = "returns a string"
  value       = alicloud_resource_manager_role.this.id
}

output "role_id" {
  description = "returns a string"
  value       = alicloud_resource_manager_role.this.role_id
}

output "update_date" {
  description = "returns a string"
  value       = alicloud_resource_manager_role.this.update_date
}

output "this" {
  value = alicloud_resource_manager_role.this
}
```

[top](#index)