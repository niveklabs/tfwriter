# fortios_vpn_ocvpn

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
module "fortios_vpn_ocvpn" {
  source = "./modules/fortios/r/fortios_vpn_ocvpn"

  # auto_discovery - (optional) is a type of string
  auto_discovery = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # eap - (optional) is a type of string
  eap = null
  # eap_users - (optional) is a type of string
  eap_users = null
  # ip_allocation_block - (optional) is a type of string
  ip_allocation_block = null
  # multipath - (optional) is a type of string
  multipath = null
  # nat - (optional) is a type of string
  nat = null
  # poll_interval - (optional) is a type of number
  poll_interval = null
  # role - (optional) is a type of string
  role = null
  # sdwan - (optional) is a type of string
  sdwan = null
  # status - (optional) is a type of string
  status = null

  forticlient_access = [{
    auth_groups = [{
      auth_group = null
      name       = null
      overlays = [{
        overlay_name = null
      }]
    }]
    psksecret = null
    status    = null
  }]

  overlays = [{
    assign_ip     = null
    id            = null
    inter_overlay = null
    ipv4_end_ip   = null
    ipv4_start_ip = null
    name          = null
    overlay_name  = null
    subnets = [{
      id        = null
      interface = null
      subnet    = null
      type      = null
    }]
  }]

  wan_interface = [{
    name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_discovery" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eap_users" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_allocation_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multipath" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "poll_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "role" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sdwan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "forticlient_access" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      auth_groups = list(object(
        {
          auth_group = string
          name       = string
          overlays = list(object(
            {
              overlay_name = string
            }
          ))
        }
      ))
      psksecret = string
      status    = string
    }
  ))
  default = []
}

variable "overlays" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      assign_ip     = string
      id            = number
      inter_overlay = string
      ipv4_end_ip   = string
      ipv4_start_ip = string
      name          = string
      overlay_name  = string
      subnets = list(object(
        {
          id        = number
          interface = string
          subnet    = string
          type      = string
        }
      ))
    }
  ))
  default = []
}

variable "wan_interface" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_vpn_ocvpn" "this" {
  # auto_discovery - (optional) is a type of string
  auto_discovery = var.auto_discovery
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # eap - (optional) is a type of string
  eap = var.eap
  # eap_users - (optional) is a type of string
  eap_users = var.eap_users
  # ip_allocation_block - (optional) is a type of string
  ip_allocation_block = var.ip_allocation_block
  # multipath - (optional) is a type of string
  multipath = var.multipath
  # nat - (optional) is a type of string
  nat = var.nat
  # poll_interval - (optional) is a type of number
  poll_interval = var.poll_interval
  # role - (optional) is a type of string
  role = var.role
  # sdwan - (optional) is a type of string
  sdwan = var.sdwan
  # status - (optional) is a type of string
  status = var.status

  dynamic "forticlient_access" {
    for_each = var.forticlient_access
    content {
      # psksecret - (optional) is a type of string
      psksecret = forticlient_access.value["psksecret"]
      # status - (optional) is a type of string
      status = forticlient_access.value["status"]

      dynamic "auth_groups" {
        for_each = forticlient_access.value.auth_groups
        content {
          # auth_group - (optional) is a type of string
          auth_group = auth_groups.value["auth_group"]
          # name - (optional) is a type of string
          name = auth_groups.value["name"]

          dynamic "overlays" {
            for_each = auth_groups.value.overlays
            content {
              # overlay_name - (optional) is a type of string
              overlay_name = overlays.value["overlay_name"]
            }
          }

        }
      }

    }
  }

  dynamic "overlays" {
    for_each = var.overlays
    content {
      # assign_ip - (optional) is a type of string
      assign_ip = overlays.value["assign_ip"]
      # id - (optional) is a type of number
      id = overlays.value["id"]
      # inter_overlay - (optional) is a type of string
      inter_overlay = overlays.value["inter_overlay"]
      # ipv4_end_ip - (optional) is a type of string
      ipv4_end_ip = overlays.value["ipv4_end_ip"]
      # ipv4_start_ip - (optional) is a type of string
      ipv4_start_ip = overlays.value["ipv4_start_ip"]
      # name - (optional) is a type of string
      name = overlays.value["name"]
      # overlay_name - (optional) is a type of string
      overlay_name = overlays.value["overlay_name"]

      dynamic "subnets" {
        for_each = overlays.value.subnets
        content {
          # id - (optional) is a type of number
          id = subnets.value["id"]
          # interface - (optional) is a type of string
          interface = subnets.value["interface"]
          # subnet - (optional) is a type of string
          subnet = subnets.value["subnet"]
          # type - (optional) is a type of string
          type = subnets.value["type"]
        }
      }

    }
  }

  dynamic "wan_interface" {
    for_each = var.wan_interface
    content {
      # name - (optional) is a type of string
      name = wan_interface.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auto_discovery" {
  description = "returns a string"
  value       = fortios_vpn_ocvpn.this.auto_discovery
}

output "eap" {
  description = "returns a string"
  value       = fortios_vpn_ocvpn.this.eap
}

output "eap_users" {
  description = "returns a string"
  value       = fortios_vpn_ocvpn.this.eap_users
}

output "id" {
  description = "returns a string"
  value       = fortios_vpn_ocvpn.this.id
}

output "ip_allocation_block" {
  description = "returns a string"
  value       = fortios_vpn_ocvpn.this.ip_allocation_block
}

output "multipath" {
  description = "returns a string"
  value       = fortios_vpn_ocvpn.this.multipath
}

output "nat" {
  description = "returns a string"
  value       = fortios_vpn_ocvpn.this.nat
}

output "poll_interval" {
  description = "returns a number"
  value       = fortios_vpn_ocvpn.this.poll_interval
}

output "role" {
  description = "returns a string"
  value       = fortios_vpn_ocvpn.this.role
}

output "sdwan" {
  description = "returns a string"
  value       = fortios_vpn_ocvpn.this.sdwan
}

output "status" {
  description = "returns a string"
  value       = fortios_vpn_ocvpn.this.status
}

output "this" {
  value = fortios_vpn_ocvpn.this
}
```

[top](#index)