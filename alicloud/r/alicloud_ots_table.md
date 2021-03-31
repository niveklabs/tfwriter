# alicloud_ots_table

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
module "alicloud_ots_table" {
  source = "./modules/alicloud/r/alicloud_ots_table"

  # deviation_cell_version_in_sec - (optional) is a type of string
  deviation_cell_version_in_sec = null
  # instance_name - (required) is a type of string
  instance_name = null
  # max_version - (required) is a type of number
  max_version = null
  # table_name - (required) is a type of string
  table_name = null
  # time_to_live - (required) is a type of number
  time_to_live = null

  primary_key = [{
    name = null
    type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "deviation_cell_version_in_sec" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_name" {
  description = "(required)"
  type        = string
}

variable "max_version" {
  description = "(required)"
  type        = number
}

variable "table_name" {
  description = "(required)"
  type        = string
}

variable "time_to_live" {
  description = "(required)"
  type        = number
}

variable "primary_key" {
  description = "nested block: NestingList, min items: 1, max items: 4"
  type = set(object(
    {
      name = string
      type = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ots_table" "this" {
  deviation_cell_version_in_sec = var.deviation_cell_version_in_sec
  instance_name                 = var.instance_name
  max_version                   = var.max_version
  table_name                    = var.table_name
  time_to_live                  = var.time_to_live

  dynamic "primary_key" {
    for_each = var.primary_key
    content {
      name = primary_key.value["name"]
      type = primary_key.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_ots_table.this.id
}

output "this" {
  value = alicloud_ots_table.this
}
```

[top](#index)