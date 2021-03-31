# avi_serviceengine

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
module "avi_serviceengine" {
  source = "./modules/avi/r/avi_serviceengine"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # container_mode - (optional) is a type of bool
  container_mode = null
  # container_type - (optional) is a type of string
  container_type = null
  # controller_created - (optional) is a type of bool
  controller_created = null
  # controller_ip - (optional) is a type of string
  controller_ip = null
  # enable_state - (optional) is a type of string
  enable_state = null
  # flavor - (optional) is a type of string
  flavor = null
  # host_ref - (optional) is a type of string
  host_ref = null
  # hypervisor - (optional) is a type of string
  hypervisor = null
  # name - (optional) is a type of string
  name = null
  # se_group_ref - (optional) is a type of string
  se_group_ref = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  data_vnics = [{
    adapter                 = null
    aggregator_chgd         = null
    can_se_dp_takeover      = null
    connected               = null
    del_pending             = null
    delete_vnic             = null
    dhcp_enabled            = null
    dp_deletion_done        = null
    enabled                 = null
    if_name                 = null
    ip6_autocfg_enabled     = null
    is_asm                  = null
    is_avi_internal_network = null
    is_hsm                  = null
    is_mgmt                 = null
    is_portchannel          = null
    link_up                 = null
    linux_name              = null
    mac_address             = null
    members = [{
      active      = null
      if_name     = null
      mac_address = null
    }]
    mtu          = null
    network_name = null
    network_ref  = null
    pci_id       = null
    port_uuid    = null
    vlan_id      = null
    vlan_interfaces = [{
      dhcp_enabled        = null
      enabled             = null
      if_name             = null
      ip6_autocfg_enabled = null
      is_mgmt             = null
      vlan_id             = null
      vnic_networks = [{
        ctlr_alloc = null
        ip = [{
          ip_addr = [{
            addr = null
            type = null
          }]
          mask = null
        }]
        mode = null
      }]
      vrf_ref = null
    }]
    vnic_networks = [{
      ctlr_alloc = null
      ip = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      mode = null
    }]
    vrf_id  = null
    vrf_ref = null
  }]

  mgmt_vnic = [{
    adapter                 = null
    aggregator_chgd         = null
    can_se_dp_takeover      = null
    connected               = null
    del_pending             = null
    delete_vnic             = null
    dhcp_enabled            = null
    dp_deletion_done        = null
    enabled                 = null
    if_name                 = null
    ip6_autocfg_enabled     = null
    is_asm                  = null
    is_avi_internal_network = null
    is_hsm                  = null
    is_mgmt                 = null
    is_portchannel          = null
    link_up                 = null
    linux_name              = null
    mac_address             = null
    members = [{
      active      = null
      if_name     = null
      mac_address = null
    }]
    mtu          = null
    network_name = null
    network_ref  = null
    pci_id       = null
    port_uuid    = null
    vlan_id      = null
    vlan_interfaces = [{
      dhcp_enabled        = null
      enabled             = null
      if_name             = null
      ip6_autocfg_enabled = null
      is_mgmt             = null
      vlan_id             = null
      vnic_networks = [{
        ctlr_alloc = null
        ip = [{
          ip_addr = [{
            addr = null
            type = null
          }]
          mask = null
        }]
        mode = null
      }]
      vrf_ref = null
    }]
    vnic_networks = [{
      ctlr_alloc = null
      ip = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      mode = null
    }]
    vrf_id  = null
    vrf_ref = null
  }]

  resources = [{
    cores_per_socket = null
    disk             = null
    hyper_threading  = null
    memory           = null
    num_vcpus        = null
    sockets          = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "container_mode" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "container_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "controller_created" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "controller_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flavor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hypervisor" {
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

variable "data_vnics" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      adapter                 = string
      aggregator_chgd         = bool
      can_se_dp_takeover      = bool
      connected               = bool
      del_pending             = bool
      delete_vnic             = bool
      dhcp_enabled            = bool
      dp_deletion_done        = bool
      enabled                 = bool
      if_name                 = string
      ip6_autocfg_enabled     = bool
      is_asm                  = bool
      is_avi_internal_network = bool
      is_hsm                  = bool
      is_mgmt                 = bool
      is_portchannel          = bool
      link_up                 = bool
      linux_name              = string
      mac_address             = string
      members = list(object(
        {
          active      = bool
          if_name     = string
          mac_address = string
        }
      ))
      mtu          = number
      network_name = string
      network_ref  = string
      pci_id       = string
      port_uuid    = string
      vlan_id      = number
      vlan_interfaces = list(object(
        {
          dhcp_enabled        = bool
          enabled             = bool
          if_name             = string
          ip6_autocfg_enabled = bool
          is_mgmt             = bool
          vlan_id             = number
          vnic_networks = list(object(
            {
              ctlr_alloc = bool
              ip = set(object(
                {
                  ip_addr = set(object(
                    {
                      addr = string
                      type = string
                    }
                  ))
                  mask = number
                }
              ))
              mode = string
            }
          ))
          vrf_ref = string
        }
      ))
      vnic_networks = list(object(
        {
          ctlr_alloc = bool
          ip = set(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          mode = string
        }
      ))
      vrf_id  = number
      vrf_ref = string
    }
  ))
  default = []
}

variable "mgmt_vnic" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      adapter                 = string
      aggregator_chgd         = bool
      can_se_dp_takeover      = bool
      connected               = bool
      del_pending             = bool
      delete_vnic             = bool
      dhcp_enabled            = bool
      dp_deletion_done        = bool
      enabled                 = bool
      if_name                 = string
      ip6_autocfg_enabled     = bool
      is_asm                  = bool
      is_avi_internal_network = bool
      is_hsm                  = bool
      is_mgmt                 = bool
      is_portchannel          = bool
      link_up                 = bool
      linux_name              = string
      mac_address             = string
      members = list(object(
        {
          active      = bool
          if_name     = string
          mac_address = string
        }
      ))
      mtu          = number
      network_name = string
      network_ref  = string
      pci_id       = string
      port_uuid    = string
      vlan_id      = number
      vlan_interfaces = list(object(
        {
          dhcp_enabled        = bool
          enabled             = bool
          if_name             = string
          ip6_autocfg_enabled = bool
          is_mgmt             = bool
          vlan_id             = number
          vnic_networks = list(object(
            {
              ctlr_alloc = bool
              ip = set(object(
                {
                  ip_addr = set(object(
                    {
                      addr = string
                      type = string
                    }
                  ))
                  mask = number
                }
              ))
              mode = string
            }
          ))
          vrf_ref = string
        }
      ))
      vnic_networks = list(object(
        {
          ctlr_alloc = bool
          ip = set(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          mode = string
        }
      ))
      vrf_id  = number
      vrf_ref = string
    }
  ))
  default = []
}

variable "resources" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cores_per_socket = number
      disk             = number
      hyper_threading  = bool
      memory           = number
      num_vcpus        = number
      sockets          = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_serviceengine" "this" {
  availability_zone  = var.availability_zone
  cloud_ref          = var.cloud_ref
  container_mode     = var.container_mode
  container_type     = var.container_type
  controller_created = var.controller_created
  controller_ip      = var.controller_ip
  enable_state       = var.enable_state
  flavor             = var.flavor
  host_ref           = var.host_ref
  hypervisor         = var.hypervisor
  name               = var.name
  se_group_ref       = var.se_group_ref
  tenant_ref         = var.tenant_ref
  uuid               = var.uuid

  dynamic "data_vnics" {
    for_each = var.data_vnics
    content {
      adapter                 = data_vnics.value["adapter"]
      aggregator_chgd         = data_vnics.value["aggregator_chgd"]
      can_se_dp_takeover      = data_vnics.value["can_se_dp_takeover"]
      connected               = data_vnics.value["connected"]
      del_pending             = data_vnics.value["del_pending"]
      delete_vnic             = data_vnics.value["delete_vnic"]
      dhcp_enabled            = data_vnics.value["dhcp_enabled"]
      dp_deletion_done        = data_vnics.value["dp_deletion_done"]
      enabled                 = data_vnics.value["enabled"]
      if_name                 = data_vnics.value["if_name"]
      ip6_autocfg_enabled     = data_vnics.value["ip6_autocfg_enabled"]
      is_asm                  = data_vnics.value["is_asm"]
      is_avi_internal_network = data_vnics.value["is_avi_internal_network"]
      is_hsm                  = data_vnics.value["is_hsm"]
      is_mgmt                 = data_vnics.value["is_mgmt"]
      is_portchannel          = data_vnics.value["is_portchannel"]
      link_up                 = data_vnics.value["link_up"]
      linux_name              = data_vnics.value["linux_name"]
      mac_address             = data_vnics.value["mac_address"]
      mtu                     = data_vnics.value["mtu"]
      network_name            = data_vnics.value["network_name"]
      network_ref             = data_vnics.value["network_ref"]
      pci_id                  = data_vnics.value["pci_id"]
      port_uuid               = data_vnics.value["port_uuid"]
      vlan_id                 = data_vnics.value["vlan_id"]
      vrf_id                  = data_vnics.value["vrf_id"]
      vrf_ref                 = data_vnics.value["vrf_ref"]

      dynamic "members" {
        for_each = data_vnics.value.members
        content {
          active      = members.value["active"]
          if_name     = members.value["if_name"]
          mac_address = members.value["mac_address"]
        }
      }

      dynamic "vlan_interfaces" {
        for_each = data_vnics.value.vlan_interfaces
        content {
          dhcp_enabled        = vlan_interfaces.value["dhcp_enabled"]
          enabled             = vlan_interfaces.value["enabled"]
          if_name             = vlan_interfaces.value["if_name"]
          ip6_autocfg_enabled = vlan_interfaces.value["ip6_autocfg_enabled"]
          is_mgmt             = vlan_interfaces.value["is_mgmt"]
          vlan_id             = vlan_interfaces.value["vlan_id"]
          vrf_ref             = vlan_interfaces.value["vrf_ref"]

          dynamic "vnic_networks" {
            for_each = vlan_interfaces.value.vnic_networks
            content {
              ctlr_alloc = vnic_networks.value["ctlr_alloc"]
              mode       = vnic_networks.value["mode"]

              dynamic "ip" {
                for_each = vnic_networks.value.ip
                content {
                  mask = ip.value["mask"]

                  dynamic "ip_addr" {
                    for_each = ip.value.ip_addr
                    content {
                      addr = ip_addr.value["addr"]
                      type = ip_addr.value["type"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "vnic_networks" {
        for_each = data_vnics.value.vnic_networks
        content {
          ctlr_alloc = vnic_networks.value["ctlr_alloc"]
          mode       = vnic_networks.value["mode"]

          dynamic "ip" {
            for_each = vnic_networks.value.ip
            content {
              mask = ip.value["mask"]

              dynamic "ip_addr" {
                for_each = ip.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "mgmt_vnic" {
    for_each = var.mgmt_vnic
    content {
      adapter                 = mgmt_vnic.value["adapter"]
      aggregator_chgd         = mgmt_vnic.value["aggregator_chgd"]
      can_se_dp_takeover      = mgmt_vnic.value["can_se_dp_takeover"]
      connected               = mgmt_vnic.value["connected"]
      del_pending             = mgmt_vnic.value["del_pending"]
      delete_vnic             = mgmt_vnic.value["delete_vnic"]
      dhcp_enabled            = mgmt_vnic.value["dhcp_enabled"]
      dp_deletion_done        = mgmt_vnic.value["dp_deletion_done"]
      enabled                 = mgmt_vnic.value["enabled"]
      if_name                 = mgmt_vnic.value["if_name"]
      ip6_autocfg_enabled     = mgmt_vnic.value["ip6_autocfg_enabled"]
      is_asm                  = mgmt_vnic.value["is_asm"]
      is_avi_internal_network = mgmt_vnic.value["is_avi_internal_network"]
      is_hsm                  = mgmt_vnic.value["is_hsm"]
      is_mgmt                 = mgmt_vnic.value["is_mgmt"]
      is_portchannel          = mgmt_vnic.value["is_portchannel"]
      link_up                 = mgmt_vnic.value["link_up"]
      linux_name              = mgmt_vnic.value["linux_name"]
      mac_address             = mgmt_vnic.value["mac_address"]
      mtu                     = mgmt_vnic.value["mtu"]
      network_name            = mgmt_vnic.value["network_name"]
      network_ref             = mgmt_vnic.value["network_ref"]
      pci_id                  = mgmt_vnic.value["pci_id"]
      port_uuid               = mgmt_vnic.value["port_uuid"]
      vlan_id                 = mgmt_vnic.value["vlan_id"]
      vrf_id                  = mgmt_vnic.value["vrf_id"]
      vrf_ref                 = mgmt_vnic.value["vrf_ref"]

      dynamic "members" {
        for_each = mgmt_vnic.value.members
        content {
          active      = members.value["active"]
          if_name     = members.value["if_name"]
          mac_address = members.value["mac_address"]
        }
      }

      dynamic "vlan_interfaces" {
        for_each = mgmt_vnic.value.vlan_interfaces
        content {
          dhcp_enabled        = vlan_interfaces.value["dhcp_enabled"]
          enabled             = vlan_interfaces.value["enabled"]
          if_name             = vlan_interfaces.value["if_name"]
          ip6_autocfg_enabled = vlan_interfaces.value["ip6_autocfg_enabled"]
          is_mgmt             = vlan_interfaces.value["is_mgmt"]
          vlan_id             = vlan_interfaces.value["vlan_id"]
          vrf_ref             = vlan_interfaces.value["vrf_ref"]

          dynamic "vnic_networks" {
            for_each = vlan_interfaces.value.vnic_networks
            content {
              ctlr_alloc = vnic_networks.value["ctlr_alloc"]
              mode       = vnic_networks.value["mode"]

              dynamic "ip" {
                for_each = vnic_networks.value.ip
                content {
                  mask = ip.value["mask"]

                  dynamic "ip_addr" {
                    for_each = ip.value.ip_addr
                    content {
                      addr = ip_addr.value["addr"]
                      type = ip_addr.value["type"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "vnic_networks" {
        for_each = mgmt_vnic.value.vnic_networks
        content {
          ctlr_alloc = vnic_networks.value["ctlr_alloc"]
          mode       = vnic_networks.value["mode"]

          dynamic "ip" {
            for_each = vnic_networks.value.ip
            content {
              mask = ip.value["mask"]

              dynamic "ip_addr" {
                for_each = ip.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "resources" {
    for_each = var.resources
    content {
      cores_per_socket = resources.value["cores_per_socket"]
      disk             = resources.value["disk"]
      hyper_threading  = resources.value["hyper_threading"]
      memory           = resources.value["memory"]
      num_vcpus        = resources.value["num_vcpus"]
      sockets          = resources.value["sockets"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "availability_zone" {
  description = "returns a string"
  value       = avi_serviceengine.this.availability_zone
}

output "cloud_ref" {
  description = "returns a string"
  value       = avi_serviceengine.this.cloud_ref
}

output "controller_ip" {
  description = "returns a string"
  value       = avi_serviceengine.this.controller_ip
}

output "flavor" {
  description = "returns a string"
  value       = avi_serviceengine.this.flavor
}

output "host_ref" {
  description = "returns a string"
  value       = avi_serviceengine.this.host_ref
}

output "hypervisor" {
  description = "returns a string"
  value       = avi_serviceengine.this.hypervisor
}

output "id" {
  description = "returns a string"
  value       = avi_serviceengine.this.id
}

output "se_group_ref" {
  description = "returns a string"
  value       = avi_serviceengine.this.se_group_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_serviceengine.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_serviceengine.this.uuid
}

output "this" {
  value = avi_serviceengine.this
}
```

[top](#index)