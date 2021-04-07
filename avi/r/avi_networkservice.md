# avi_networkservice

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_networkservice" {
  source = "./modules/avi/r/avi_networkservice"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # name - (optional) is a type of string
  name = null
  # se_group_ref - (optional) is a type of string
  se_group_ref = null
  # service_type - (optional) is a type of string
  service_type = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
  # vrf_ref - (optional) is a type of string
  vrf_ref = null

  routing_service = [{
    advertise_backend_networks   = null
    enable_routing               = null
    enable_vip_on_all_interfaces = null
    enable_vmac                  = null
    floating_intf_ip = [{
      addr = null
      type = null
    }]
    floating_intf_ip_se_2 = [{
      addr = null
      type = null
    }]
    flowtable_profile = [{
      tcp_closed_timeout           = null
      tcp_connection_setup_timeout = null
      tcp_half_closed_timeout      = null
      tcp_idle_timeout             = null
      tcp_reset_timeout            = null
      udp_idle_timeout             = null
    }]
    graceful_restart         = null
    nat_policy_ref           = null
    routing_by_linux_ipstack = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "se_group_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrf_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "routing_service" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      advertise_backend_networks   = bool
      enable_routing               = bool
      enable_vip_on_all_interfaces = bool
      enable_vmac                  = bool
      floating_intf_ip = list(object(
        {
          addr = string
          type = string
        }
      ))
      floating_intf_ip_se_2 = list(object(
        {
          addr = string
          type = string
        }
      ))
      flowtable_profile = set(object(
        {
          tcp_closed_timeout           = number
          tcp_connection_setup_timeout = number
          tcp_half_closed_timeout      = number
          tcp_idle_timeout             = number
          tcp_reset_timeout            = number
          udp_idle_timeout             = number
        }
      ))
      graceful_restart         = bool
      nat_policy_ref           = string
      routing_by_linux_ipstack = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_networkservice" "this" {
  # cloud_ref - (optional) is a type of string
  cloud_ref = var.cloud_ref
  # name - (optional) is a type of string
  name = var.name
  # se_group_ref - (optional) is a type of string
  se_group_ref = var.se_group_ref
  # service_type - (optional) is a type of string
  service_type = var.service_type
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # vrf_ref - (optional) is a type of string
  vrf_ref = var.vrf_ref

  dynamic "routing_service" {
    for_each = var.routing_service
    content {
      # advertise_backend_networks - (optional) is a type of bool
      advertise_backend_networks = routing_service.value["advertise_backend_networks"]
      # enable_routing - (optional) is a type of bool
      enable_routing = routing_service.value["enable_routing"]
      # enable_vip_on_all_interfaces - (optional) is a type of bool
      enable_vip_on_all_interfaces = routing_service.value["enable_vip_on_all_interfaces"]
      # enable_vmac - (optional) is a type of bool
      enable_vmac = routing_service.value["enable_vmac"]
      # graceful_restart - (optional) is a type of bool
      graceful_restart = routing_service.value["graceful_restart"]
      # nat_policy_ref - (optional) is a type of string
      nat_policy_ref = routing_service.value["nat_policy_ref"]
      # routing_by_linux_ipstack - (optional) is a type of bool
      routing_by_linux_ipstack = routing_service.value["routing_by_linux_ipstack"]

      dynamic "floating_intf_ip" {
        for_each = routing_service.value.floating_intf_ip
        content {
          # addr - (required) is a type of string
          addr = floating_intf_ip.value["addr"]
          # type - (required) is a type of string
          type = floating_intf_ip.value["type"]
        }
      }

      dynamic "floating_intf_ip_se_2" {
        for_each = routing_service.value.floating_intf_ip_se_2
        content {
          # addr - (required) is a type of string
          addr = floating_intf_ip_se_2.value["addr"]
          # type - (required) is a type of string
          type = floating_intf_ip_se_2.value["type"]
        }
      }

      dynamic "flowtable_profile" {
        for_each = routing_service.value.flowtable_profile
        content {
          # tcp_closed_timeout - (optional) is a type of number
          tcp_closed_timeout = flowtable_profile.value["tcp_closed_timeout"]
          # tcp_connection_setup_timeout - (optional) is a type of number
          tcp_connection_setup_timeout = flowtable_profile.value["tcp_connection_setup_timeout"]
          # tcp_half_closed_timeout - (optional) is a type of number
          tcp_half_closed_timeout = flowtable_profile.value["tcp_half_closed_timeout"]
          # tcp_idle_timeout - (optional) is a type of number
          tcp_idle_timeout = flowtable_profile.value["tcp_idle_timeout"]
          # tcp_reset_timeout - (optional) is a type of number
          tcp_reset_timeout = flowtable_profile.value["tcp_reset_timeout"]
          # udp_idle_timeout - (optional) is a type of number
          udp_idle_timeout = flowtable_profile.value["udp_idle_timeout"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_ref" {
  description = "returns a string"
  value       = avi_networkservice.this.cloud_ref
}

output "id" {
  description = "returns a string"
  value       = avi_networkservice.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_networkservice.this.name
}

output "se_group_ref" {
  description = "returns a string"
  value       = avi_networkservice.this.se_group_ref
}

output "service_type" {
  description = "returns a string"
  value       = avi_networkservice.this.service_type
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_networkservice.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_networkservice.this.uuid
}

output "vrf_ref" {
  description = "returns a string"
  value       = avi_networkservice.this.vrf_ref
}

output "this" {
  value = avi_networkservice.this
}
```

[top](#index)