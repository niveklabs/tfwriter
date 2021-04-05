# alicloud_cen_private_zone

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
module "alicloud_cen_private_zone" {
  source = "./modules/alicloud/r/alicloud_cen_private_zone"

  # access_region_id - (required) is a type of string
  access_region_id = null
  # cen_id - (required) is a type of string
  cen_id = null
  # host_region_id - (required) is a type of string
  host_region_id = null
  # host_vpc_id - (required) is a type of string
  host_vpc_id = null

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "access_region_id" {
  description = "(required)"
  type        = string
}

variable "cen_id" {
  description = "(required)"
  type        = string
}

variable "host_region_id" {
  description = "(required)"
  type        = string
}

variable "host_vpc_id" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cen_private_zone" "this" {
  access_region_id = var.access_region_id
  cen_id           = var.cen_id
  host_region_id   = var.host_region_id
  host_vpc_id      = var.host_vpc_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_cen_private_zone.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_cen_private_zone.this.status
}

output "this" {
  value = alicloud_cen_private_zone.this
}
```

[top](#index)