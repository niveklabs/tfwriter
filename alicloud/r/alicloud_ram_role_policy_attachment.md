# alicloud_ram_role_policy_attachment

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
module "alicloud_ram_role_policy_attachment" {
  source = "./modules/alicloud/r/alicloud_ram_role_policy_attachment"

  # policy_name - (required) is a type of string
  policy_name = null
  # policy_type - (required) is a type of string
  policy_type = null
  # role_name - (required) is a type of string
  role_name = null
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

variable "role_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_role_policy_attachment" "this" {
  policy_name = var.policy_name
  policy_type = var.policy_type
  role_name   = var.role_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ram_role_policy_attachment.this.id
}

output "this" {
  value = alicloud_ram_role_policy_attachment.this
}
```

[top](#index)