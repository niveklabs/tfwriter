# alicloud_cen_route_service

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_cen_route_service" {
  source = "./modules/alicloud/r/alicloud_cen_route_service"

  # access_region_id - (required) is a type of string
  access_region_id = null
  # cen_id - (required) is a type of string
  cen_id = null
  # description - (optional) is a type of string
  description = null
  # host - (required) is a type of string
  host = null
  # host_region_id - (required) is a type of string
  host_region_id = null
  # host_vpc_id - (required) is a type of string
  host_vpc_id = null

  timeouts = [{
    create = null
    delete = null
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host" {
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
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_cen_route_service" "this" {
  access_region_id = var.access_region_id
  cen_id           = var.cen_id
  description      = var.description
  host             = var.host
  host_region_id   = var.host_region_id
  host_vpc_id      = var.host_vpc_id

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
  value       = alicloud_cen_route_service.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_cen_route_service.this.status
}

output "this" {
  value = alicloud_cen_route_service.this
}
```

[top](#index)