# ecl_network_subnet_v2

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
    ecl = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_network_subnet_v2" {
  source = "./modules/ecl/r/ecl_network_subnet_v2"

  # cidr - (required) is a type of string
  cidr = null
  # description - (optional) is a type of string
  description = null
  # dns_nameservers - (optional) is a type of list of string
  dns_nameservers = []
  # enable_dhcp - (optional) is a type of bool
  enable_dhcp = null
  # gateway_ip - (optional) is a type of string
  gateway_ip = null
  # ip_version - (optional) is a type of number
  ip_version = null
  # name - (optional) is a type of string
  name = null
  # network_id - (required) is a type of string
  network_id = null
  # no_gateway - (optional) is a type of bool
  no_gateway = null
  # ntp_servers - (optional) is a type of list of string
  ntp_servers = []
  # region - (optional) is a type of string
  region = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tenant_id - (optional) is a type of string
  tenant_id = null

  allocation_pools = [{
    end   = null
    start = null
  }]

  host_routes = [{
    destination_cidr = null
    next_hop         = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cidr" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_nameservers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "enable_dhcp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "gateway_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_version" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_id" {
  description = "(required)"
  type        = string
}

variable "no_gateway" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ntp_servers" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tenant_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allocation_pools" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      end   = string
      start = string
    }
  ))
  default = []
}

variable "host_routes" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      destination_cidr = string
      next_hop         = string
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_network_subnet_v2" "this" {
  cidr            = var.cidr
  description     = var.description
  dns_nameservers = var.dns_nameservers
  enable_dhcp     = var.enable_dhcp
  gateway_ip      = var.gateway_ip
  ip_version      = var.ip_version
  name            = var.name
  network_id      = var.network_id
  no_gateway      = var.no_gateway
  ntp_servers     = var.ntp_servers
  region          = var.region
  tags            = var.tags
  tenant_id       = var.tenant_id

  dynamic "allocation_pools" {
    for_each = var.allocation_pools
    content {
      end   = allocation_pools.value["end"]
      start = allocation_pools.value["start"]
    }
  }

  dynamic "host_routes" {
    for_each = var.host_routes
    content {
      destination_cidr = host_routes.value["destination_cidr"]
      next_hop         = host_routes.value["next_hop"]
    }
  }

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
output "dns_nameservers" {
  description = "returns a list of string"
  value       = ecl_network_subnet_v2.this.dns_nameservers
}

output "enable_dhcp" {
  description = "returns a bool"
  value       = ecl_network_subnet_v2.this.enable_dhcp
}

output "gateway_ip" {
  description = "returns a string"
  value       = ecl_network_subnet_v2.this.gateway_ip
}

output "id" {
  description = "returns a string"
  value       = ecl_network_subnet_v2.this.id
}

output "ipv6_address_mode" {
  description = "returns a string"
  value       = ecl_network_subnet_v2.this.ipv6_address_mode
}

output "ipv6_ra_mode" {
  description = "returns a string"
  value       = ecl_network_subnet_v2.this.ipv6_ra_mode
}

output "region" {
  description = "returns a string"
  value       = ecl_network_subnet_v2.this.region
}

output "status" {
  description = "returns a string"
  value       = ecl_network_subnet_v2.this.status
}

output "tenant_id" {
  description = "returns a string"
  value       = ecl_network_subnet_v2.this.tenant_id
}

output "this" {
  value = ecl_network_subnet_v2.this
}
```

[top](#index)