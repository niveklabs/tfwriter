# alicloud_route_table_attachment

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
module "alicloud_route_table_attachment" {
  source = "./modules/alicloud/r/alicloud_route_table_attachment"

  # route_table_id - (required) is a type of string
  route_table_id = null
  # vswitch_id - (required) is a type of string
  vswitch_id = null
}
```

[top](#index)

### Variables

```terraform
variable "route_table_id" {
  description = "(required)"
  type        = string
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_route_table_attachment" "this" {
  # route_table_id - (required) is a type of string
  route_table_id = var.route_table_id
  # vswitch_id - (required) is a type of string
  vswitch_id = var.vswitch_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_route_table_attachment.this.id
}

output "this" {
  value = alicloud_route_table_attachment.this
}
```

[top](#index)