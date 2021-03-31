# alicloud_drds_instance

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
module "alicloud_drds_instance" {
  source = "./modules/alicloud/r/alicloud_drds_instance"

  # description - (required) is a type of string
  description = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # instance_series - (required) is a type of string
  instance_series = null
  # specification - (required) is a type of string
  specification = null
  # vswitch_id - (required) is a type of string
  vswitch_id = null
  # zone_id - (required) is a type of string
  zone_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(required)"
  type        = string
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_series" {
  description = "(required)"
  type        = string
}

variable "specification" {
  description = "(required)"
  type        = string
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_drds_instance" "this" {
  description          = var.description
  instance_charge_type = var.instance_charge_type
  instance_series      = var.instance_series
  specification        = var.specification
  vswitch_id           = var.vswitch_id
  zone_id              = var.zone_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_drds_instance.this.id
}

output "this" {
  value = alicloud_drds_instance.this
}
```

[top](#index)