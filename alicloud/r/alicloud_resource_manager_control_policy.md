# alicloud_resource_manager_control_policy

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
module "alicloud_resource_manager_control_policy" {
  source = "./modules/alicloud/r/alicloud_resource_manager_control_policy"

  # control_policy_name - (required) is a type of string
  control_policy_name = null
  # description - (optional) is a type of string
  description = null
  # effect_scope - (required) is a type of string
  effect_scope = null
  # policy_document - (required) is a type of string
  policy_document = null
}
```

[top](#index)

### Variables

```terraform
variable "control_policy_name" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "effect_scope" {
  description = "(required)"
  type        = string
}

variable "policy_document" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_resource_manager_control_policy" "this" {
  control_policy_name = var.control_policy_name
  description         = var.description
  effect_scope        = var.effect_scope
  policy_document     = var.policy_document
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_resource_manager_control_policy.this.id
}

output "this" {
  value = alicloud_resource_manager_control_policy.this
}
```

[top](#index)