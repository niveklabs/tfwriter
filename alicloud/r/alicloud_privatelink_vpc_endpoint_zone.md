# alicloud_privatelink_vpc_endpoint_zone

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
module "alicloud_privatelink_vpc_endpoint_zone" {
  source = "./modules/alicloud/r/alicloud_privatelink_vpc_endpoint_zone"

  # dry_run - (optional) is a type of bool
  dry_run = null
  # endpoint_id - (required) is a type of string
  endpoint_id = null
  # vswitch_id - (required) is a type of string
  vswitch_id = null
  # zone_id - (optional) is a type of string
  zone_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "endpoint_id" {
  description = "(required)"
  type        = string
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_privatelink_vpc_endpoint_zone" "this" {
  dry_run     = var.dry_run
  endpoint_id = var.endpoint_id
  vswitch_id  = var.vswitch_id
  zone_id     = var.zone_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint_zone.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint_zone.this.status
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_privatelink_vpc_endpoint_zone.this.zone_id
}

output "this" {
  value = alicloud_privatelink_vpc_endpoint_zone.this
}
```

[top](#index)