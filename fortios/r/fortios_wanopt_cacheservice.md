# fortios_wanopt_cacheservice

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wanopt_cacheservice" {
  source = "./modules/fortios/r/fortios_wanopt_cacheservice"

  # acceptable_connections - (optional) is a type of string
  acceptable_connections = null
  # collaboration - (optional) is a type of string
  collaboration = null
  # device_id - (optional) is a type of string
  device_id = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # prefer_scenario - (optional) is a type of string
  prefer_scenario = null

  dst_peer = [{
    auth_type   = null
    device_id   = null
    encode_type = null
    ip          = null
    priority    = null
  }]

  src_peer = [{
    auth_type   = null
    device_id   = null
    encode_type = null
    ip          = null
    priority    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acceptable_connections" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "collaboration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "prefer_scenario" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dst_peer" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_type   = number
      device_id   = string
      encode_type = number
      ip          = string
      priority    = number
    }
  ))
  default = []
}

variable "src_peer" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_type   = number
      device_id   = string
      encode_type = number
      ip          = string
      priority    = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wanopt_cacheservice" "this" {
  acceptable_connections = var.acceptable_connections
  collaboration          = var.collaboration
  device_id              = var.device_id
  dynamic_sort_subtable  = var.dynamic_sort_subtable
  prefer_scenario        = var.prefer_scenario

  dynamic "dst_peer" {
    for_each = var.dst_peer
    content {
      auth_type   = dst_peer.value["auth_type"]
      device_id   = dst_peer.value["device_id"]
      encode_type = dst_peer.value["encode_type"]
      ip          = dst_peer.value["ip"]
      priority    = dst_peer.value["priority"]
    }
  }

  dynamic "src_peer" {
    for_each = var.src_peer
    content {
      auth_type   = src_peer.value["auth_type"]
      device_id   = src_peer.value["device_id"]
      encode_type = src_peer.value["encode_type"]
      ip          = src_peer.value["ip"]
      priority    = src_peer.value["priority"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "acceptable_connections" {
  description = "returns a string"
  value       = fortios_wanopt_cacheservice.this.acceptable_connections
}

output "collaboration" {
  description = "returns a string"
  value       = fortios_wanopt_cacheservice.this.collaboration
}

output "device_id" {
  description = "returns a string"
  value       = fortios_wanopt_cacheservice.this.device_id
}

output "id" {
  description = "returns a string"
  value       = fortios_wanopt_cacheservice.this.id
}

output "prefer_scenario" {
  description = "returns a string"
  value       = fortios_wanopt_cacheservice.this.prefer_scenario
}

output "this" {
  value = fortios_wanopt_cacheservice.this
}
```

[top](#index)