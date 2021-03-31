# nsxt_logical_dhcp_server

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_logical_dhcp_server" {
  source = "./modules/nsxt/r/nsxt_logical_dhcp_server"

  # description - (optional) is a type of string
  description = null
  # dhcp_profile_id - (required) is a type of string
  dhcp_profile_id = null
  # dhcp_server_ip - (required) is a type of string
  dhcp_server_ip = null
  # display_name - (optional) is a type of string
  display_name = null
  # dns_name_servers - (optional) is a type of list of string
  dns_name_servers = []
  # domain_name - (optional) is a type of string
  domain_name = null
  # gateway_ip - (optional) is a type of string
  gateway_ip = null

  dhcp_generic_option = [{
    code   = null
    values = []
  }]

  dhcp_option_121 = [{
    network  = null
    next_hop = null
  }]

  tag = [{
    scope = null
    tag   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "dhcp_profile_id" {
  description = "(required) - DHCP profile uuid"
  type        = string
}

variable "dhcp_server_ip" {
  description = "(required) - DHCP server ip in cidr format"
  type        = string
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "dns_name_servers" {
  description = "(optional) - DNS IPs"
  type        = list(string)
  default     = null
}

variable "domain_name" {
  description = "(optional) - Domain name"
  type        = string
  default     = null
}

variable "gateway_ip" {
  description = "(optional) - Gateway IP"
  type        = string
  default     = null
}

variable "dhcp_generic_option" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      code   = number
      values = list(string)
    }
  ))
  default = []
}

variable "dhcp_option_121" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      network  = string
      next_hop = string
    }
  ))
  default = []
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_logical_dhcp_server" "this" {
  description      = var.description
  dhcp_profile_id  = var.dhcp_profile_id
  dhcp_server_ip   = var.dhcp_server_ip
  display_name     = var.display_name
  dns_name_servers = var.dns_name_servers
  domain_name      = var.domain_name
  gateway_ip       = var.gateway_ip

  dynamic "dhcp_generic_option" {
    for_each = var.dhcp_generic_option
    content {
      code   = dhcp_generic_option.value["code"]
      values = dhcp_generic_option.value["values"]
    }
  }

  dynamic "dhcp_option_121" {
    for_each = var.dhcp_option_121
    content {
      network  = dhcp_option_121.value["network"]
      next_hop = dhcp_option_121.value["next_hop"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "attached_logical_port_id" {
  description = "returns a string"
  value       = nsxt_logical_dhcp_server.this.attached_logical_port_id
}

output "display_name" {
  description = "returns a string"
  value       = nsxt_logical_dhcp_server.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_logical_dhcp_server.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_logical_dhcp_server.this.revision
}

output "this" {
  value = nsxt_logical_dhcp_server.this
}
```

[top](#index)