# vcd_network_isolated_v2

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_network_isolated_v2" {
  source = "./modules/vcd/r/vcd_network_isolated_v2"

  # description - (optional) is a type of string
  description = null
  # dns1 - (optional) is a type of string
  dns1 = null
  # dns2 - (optional) is a type of string
  dns2 = null
  # dns_suffix - (optional) is a type of string
  dns_suffix = null
  # gateway - (required) is a type of string
  gateway = null
  # is_shared - (optional) is a type of bool
  is_shared = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # prefix_length - (required) is a type of number
  prefix_length = null
  # vdc - (optional) is a type of string
  vdc = null

  static_ip_pool = [{
    end_address   = null
    start_address = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Network description"
  type        = string
  default     = null
}

variable "dns1" {
  description = "(optional) - DNS server 1"
  type        = string
  default     = null
}

variable "dns2" {
  description = "(optional) - DNS server 1"
  type        = string
  default     = null
}

variable "dns_suffix" {
  description = "(optional) - DNS suffix"
  type        = string
  default     = null
}

variable "gateway" {
  description = "(required) - Gateway IP address"
  type        = string
}

variable "is_shared" {
  description = "(optional) - NSX-V only - share this network with other VDCs in this organization. Default - false"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Network name"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "prefix_length" {
  description = "(required) - Network prefix"
  type        = number
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "static_ip_pool" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      end_address   = string
      start_address = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vcd_network_isolated_v2" "this" {
  # description - (optional) is a type of string
  description = var.description
  # dns1 - (optional) is a type of string
  dns1 = var.dns1
  # dns2 - (optional) is a type of string
  dns2 = var.dns2
  # dns_suffix - (optional) is a type of string
  dns_suffix = var.dns_suffix
  # gateway - (required) is a type of string
  gateway = var.gateway
  # is_shared - (optional) is a type of bool
  is_shared = var.is_shared
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # prefix_length - (required) is a type of number
  prefix_length = var.prefix_length
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "static_ip_pool" {
    for_each = var.static_ip_pool
    content {
      # end_address - (required) is a type of string
      end_address = static_ip_pool.value["end_address"]
      # start_address - (required) is a type of string
      start_address = static_ip_pool.value["start_address"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_network_isolated_v2.this.id
}

output "this" {
  value = vcd_network_isolated_v2.this
}
```

[top](#index)