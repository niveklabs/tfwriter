# alicloud_resource_manager_policy_attachment

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
module "alicloud_resource_manager_policy_attachment" {
  source = "./modules/alicloud/r/alicloud_resource_manager_policy_attachment"

  # policy_name - (required) is a type of string
  policy_name = null
  # policy_type - (required) is a type of string
  policy_type = null
  # principal_name - (required) is a type of string
  principal_name = null
  # principal_type - (required) is a type of string
  principal_type = null
  # resource_group_id - (required) is a type of string
  resource_group_id = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_name" {
  description = "(required)"
  type        = string
}

variable "policy_type" {
  description = "(required)"
  type        = string
}

variable "principal_name" {
  description = "(required)"
  type        = string
}

variable "principal_type" {
  description = "(required)"
  type        = string
}

variable "resource_group_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_resource_manager_policy_attachment" "this" {
  # policy_name - (required) is a type of string
  policy_name = var.policy_name
  # policy_type - (required) is a type of string
  policy_type = var.policy_type
  # principal_name - (required) is a type of string
  principal_name = var.principal_name
  # principal_type - (required) is a type of string
  principal_type = var.principal_type
  # resource_group_id - (required) is a type of string
  resource_group_id = var.resource_group_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_resource_manager_policy_attachment.this.id
}

output "this" {
  value = alicloud_resource_manager_policy_attachment.this
}
```

[top](#index)