# vcd_nsxv_dhcp_relay

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
module "vcd_nsxv_dhcp_relay" {
  source = "./modules/vcd/r/vcd_nsxv_dhcp_relay"

  # domain_names - (optional) is a type of set of string
  domain_names = []
  # edge_gateway - (required) is a type of string
  edge_gateway = null
  # ip_addresses - (optional) is a type of set of string
  ip_addresses = []
  # ip_sets - (optional) is a type of set of string
  ip_sets = []
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null

  relay_agent = [{
    gateway_ip_address = null
    network_name       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "domain_names" {
  description = "(optional) - A set of IP domain names of DHCP servers"
  type        = set(string)
  default     = null
}

variable "edge_gateway" {
  description = "(required) - Edge gateway name for DHCP relay settings"
  type        = string
}

variable "ip_addresses" {
  description = "(optional) - A set of IP address of DHCP servers"
  type        = set(string)
  default     = null
}

variable "ip_sets" {
  description = "(optional) - A set of IP set names which consist DHCP servers"
  type        = set(string)
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "relay_agent" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      gateway_ip_address = string
      network_name       = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "vcd_nsxv_dhcp_relay" "this" {
  # domain_names - (optional) is a type of set of string
  domain_names = var.domain_names
  # edge_gateway - (required) is a type of string
  edge_gateway = var.edge_gateway
  # ip_addresses - (optional) is a type of set of string
  ip_addresses = var.ip_addresses
  # ip_sets - (optional) is a type of set of string
  ip_sets = var.ip_sets
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "relay_agent" {
    for_each = var.relay_agent
    content {
      # gateway_ip_address - (optional) is a type of string
      gateway_ip_address = relay_agent.value["gateway_ip_address"]
      # network_name - (required) is a type of string
      network_name = relay_agent.value["network_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_nsxv_dhcp_relay.this.id
}

output "this" {
  value = vcd_nsxv_dhcp_relay.this
}
```

[top](#index)