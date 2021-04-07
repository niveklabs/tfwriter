# alicloud_resource_manager_policy

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
module "alicloud_resource_manager_policy" {
  source = "./modules/alicloud/r/alicloud_resource_manager_policy"

  # default_version - (optional) is a type of string
  default_version = null
  # description - (optional) is a type of string
  description = null
  # policy_document - (required) is a type of string
  policy_document = null
  # policy_name - (required) is a type of string
  policy_name = null
}
```

[top](#index)

### Variables

```terraform
variable "default_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
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
resource "alicloud_resource_manager_policy" "this" {
  # default_version - (optional) is a type of string
  default_version = var.default_version
  # description - (optional) is a type of string
  description = var.description
  # policy_document - (required) is a type of string
  policy_document = var.policy_document
  # policy_name - (required) is a type of string
  policy_name = var.policy_name
}
```

[top](#index)

### Outputs

```terraform
output "default_version" {
  description = "returns a string"
  value       = alicloud_resource_manager_policy.this.default_version
}

output "id" {
  description = "returns a string"
  value       = alicloud_resource_manager_policy.this.id
}

output "policy_type" {
  description = "returns a string"
  value       = alicloud_resource_manager_policy.this.policy_type
}

output "this" {
  value = alicloud_resource_manager_policy.this
}
```

[top](#index)