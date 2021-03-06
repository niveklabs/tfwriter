# alicloud_resource_manager_control_policy_attachment

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
module "alicloud_resource_manager_control_policy_attachment" {
  source = "./modules/alicloud/r/alicloud_resource_manager_control_policy_attachment"

  # policy_id - (required) is a type of string
  policy_id = null
  # target_id - (required) is a type of string
  target_id = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_id" {
  description = "(required)"
  type        = string
}

variable "target_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_resource_manager_control_policy_attachment" "this" {
  # policy_id - (required) is a type of string
  policy_id = var.policy_id
  # target_id - (required) is a type of string
  target_id = var.target_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_resource_manager_control_policy_attachment.this.id
}

output "this" {
  value = alicloud_resource_manager_control_policy_attachment.this
}
```

[top](#index)