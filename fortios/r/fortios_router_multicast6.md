# fortios_router_multicast6

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
module "fortios_router_multicast6" {
  source = "./modules/fortios/r/fortios_router_multicast6"

  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # multicast_pmtu - (optional) is a type of string
  multicast_pmtu = null
  # multicast_routing - (optional) is a type of string
  multicast_routing = null

  interface = [{
    hello_holdtime = null
    hello_interval = null
    name           = null
  }]

  pim_sm_global = [{
    register_rate_limit = null
    rp_address = [{
      id          = null
      ip6_address = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_pmtu" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_routing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      hello_holdtime = number
      hello_interval = number
      name           = string
    }
  ))
  default = []
}

variable "pim_sm_global" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      register_rate_limit = number
      rp_address = list(object(
        {
          id          = number
          ip6_address = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_router_multicast6" "this" {
  dynamic_sort_subtable = var.dynamic_sort_subtable
  multicast_pmtu        = var.multicast_pmtu
  multicast_routing     = var.multicast_routing

  dynamic "interface" {
    for_each = var.interface
    content {
      hello_holdtime = interface.value["hello_holdtime"]
      hello_interval = interface.value["hello_interval"]
      name           = interface.value["name"]
    }
  }

  dynamic "pim_sm_global" {
    for_each = var.pim_sm_global
    content {
      register_rate_limit = pim_sm_global.value["register_rate_limit"]

      dynamic "rp_address" {
        for_each = pim_sm_global.value.rp_address
        content {
          id          = rp_address.value["id"]
          ip6_address = rp_address.value["ip6_address"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_router_multicast6.this.id
}

output "multicast_pmtu" {
  description = "returns a string"
  value       = fortios_router_multicast6.this.multicast_pmtu
}

output "multicast_routing" {
  description = "returns a string"
  value       = fortios_router_multicast6.this.multicast_routing
}

output "this" {
  value = fortios_router_multicast6.this
}
```

[top](#index)