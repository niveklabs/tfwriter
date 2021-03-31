# alicloud_resource_manager_policy_version

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_resource_manager_policy_version" {
  source = "./modules/alicloud/r/alicloud_resource_manager_policy_version"

  # is_default_version - (optional) is a type of bool
  is_default_version = null
  # policy_document - (required) is a type of string
  policy_document = null
  # policy_name - (required) is a type of string
  policy_name = null
}
```

[top](#index)

### Variables

```terraform
variable "is_default_version" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "policy_document" {
  description = "(required)"
  type        = string
}

variable "policy_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_resource_manager_policy_version" "this" {
  is_default_version = var.is_default_version
  policy_document    = var.policy_document
  policy_name        = var.policy_name
}
```

[top](#index)

### Outputs

```terraform
output "create_date" {
  description = "returns a string"
  value       = alicloud_resource_manager_policy_version.this.create_date
}

output "id" {
  description = "returns a string"
  value       = alicloud_resource_manager_policy_version.this.id
}

output "version_id" {
  description = "returns a string"
  value       = alicloud_resource_manager_policy_version.this.version_id
}

output "this" {
  value = alicloud_resource_manager_policy_version.this
}
```

[top](#index)