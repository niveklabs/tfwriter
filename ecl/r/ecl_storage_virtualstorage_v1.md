# ecl_storage_virtualstorage_v1

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_storage_virtualstorage_v1" {
  source = "./modules/ecl/r/ecl_storage_virtualstorage_v1"

  # description - (optional) is a type of string
  description = null
  # error_message - (optional) is a type of string
  error_message = null
  # ip_addr_pool - (required) is a type of map of string
  ip_addr_pool = {}
  # name - (required) is a type of string
  name = null
  # network_id - (required) is a type of string
  network_id = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # volume_type_id - (optional) is a type of string
  volume_type_id = null
  # volume_type_name - (optional) is a type of string
  volume_type_name = null

  host_routes = [{
    destination = null
    nexthop     = null
  }]

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
  description = "(optional)"
  type        = string
  default     = null
}

variable "error_message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_addr_pool" {
  description = "(required)"
  type        = map(string)
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_id" {
  description = "(required)"
  type        = string
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "volume_type_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "volume_type_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_routes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      destination = string
      nexthop     = string
    }
  ))
  default = []
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
resource "ecl_storage_virtualstorage_v1" "this" {
  description      = var.description
  error_message    = var.error_message
  ip_addr_pool     = var.ip_addr_pool
  name             = var.name
  network_id       = var.network_id
  subnet_id        = var.subnet_id
  volume_type_id   = var.volume_type_id
  volume_type_name = var.volume_type_name

  dynamic "host_routes" {
    for_each = var.host_routes
    content {
      destination = host_routes.value["destination"]
      nexthop     = host_routes.value["nexthop"]
    }
  }

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
output "error_message" {
  description = "returns a string"
  value       = ecl_storage_virtualstorage_v1.this.error_message
}

output "id" {
  description = "returns a string"
  value       = ecl_storage_virtualstorage_v1.this.id
}

output "volume_type_id" {
  description = "returns a string"
  value       = ecl_storage_virtualstorage_v1.this.volume_type_id
}

output "this" {
  value = ecl_storage_virtualstorage_v1.this
}
```

[top](#index)