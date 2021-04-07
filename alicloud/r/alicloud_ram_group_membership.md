# alicloud_ram_group_membership

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
module "alicloud_ram_group_membership" {
  source = "./modules/alicloud/r/alicloud_ram_group_membership"

  # group_name - (required) is a type of string
  group_name = null
  # user_names - (required) is a type of set of string
  user_names = []
}
```

[top](#index)

### Variables

```terraform
variable "group_name" {
  description = "(required)"
  type        = string
}

variable "user_names" {
  description = "(required)"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ram_group_membership" "this" {
  # group_name - (required) is a type of string
  group_name = var.group_name
  # user_names - (required) is a type of set of string
  user_names = var.user_names
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ram_group_membership.this.id
}

output "this" {
  value = alicloud_ram_group_membership.this
}
```

[top](#index)