# fortios_switchcontroller_managedswitch

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_switchcontroller_managedswitch" {
  source = "./modules/fortios/r/fortios_switchcontroller_managedswitch"

  # delayed_restart_trigger - (optional) is a type of number
  delayed_restart_trigger = null
  # description - (optional) is a type of string
  description = null
  # directly_connected - (optional) is a type of number
  directly_connected = null
  # dynamic_capability - (optional) is a type of number
  dynamic_capability = null
  # dynamically_discovered - (optional) is a type of number
  dynamically_discovered = null
  # fsw_wan1_admin - (optional) is a type of string
  fsw_wan1_admin = null
  # fsw_wan1_peer - (required) is a type of string
  fsw_wan1_peer = null
  # fsw_wan2_admin - (optional) is a type of string
  fsw_wan2_admin = null
  # fsw_wan2_peer - (optional) is a type of string
  fsw_wan2_peer = null
  # max_allowed_trunk_members - (optional) is a type of number
  max_allowed_trunk_members = null
  # name - (optional) is a type of string
  name = null
  # owner_vdom - (optional) is a type of string
  owner_vdom = null
  # poe_pre_standard_detection - (optional) is a type of string
  poe_pre_standard_detection = null
  # pre_provisioned - (optional) is a type of number
  pre_provisioned = null
  # staged_image_version - (optional) is a type of string
  staged_image_version = null
  # switch_device_tag - (optional) is a type of string
  switch_device_tag = null
  # switch_id - (required) is a type of string
  switch_id = null
  # switch_profile - (optional) is a type of string
  switch_profile = null
  # type - (optional) is a type of string
  type = null
  # version - (optional) is a type of number
  version = null

  custom_command = [{
    command_entry = null
    command_name  = null
  }]

  igmp_snooping = [{
    aging_time              = null
    flood_unknown_multicast = null
    local_override          = null
  }]

  mirror = [{
    dst  = null
    name = null
    src_egress = [{
      name = null
    }]
    src_ingress = [{
      name = null
    }]
    status           = null
    switching_packet = null
  }]

  n802_1x_settings = [{
    link_down_auth     = null
    local_override     = null
    max_reauth_attempt = null
    reauth_period      = null
  }]

  ports = [{
    allowed_vlans = [{
      vlan_name = null
    }]
    allowed_vlans_all         = null
    arp_inspection_trust      = null
    bundle                    = null
    description               = null
    dhcp_snoop_option82_trust = null
    dhcp_snooping             = null
    discard_mode              = null
    edge_port                 = null
    export_tags = [{
      tag_name = null
    }]
    export_to                  = null
    export_to_pool             = null
    export_to_pool_flag        = null
    fgt_peer_device_name       = null
    fgt_peer_port_name         = null
    fiber_port                 = null
    flags                      = null
    fortilink_port             = null
    igmp_snooping              = null
    igmps_flood_reports        = null
    igmps_flood_traffic        = null
    isl_local_trunk_name       = null
    isl_peer_device_name       = null
    isl_peer_port_name         = null
    lacp_speed                 = null
    learning_limit             = null
    lldp_profile               = null
    lldp_status                = null
    loop_guard                 = null
    loop_guard_timeout         = null
    max_bundle                 = null
    mclag                      = null
    member_withdrawal_behavior = null
    members = [{
      member_name = null
    }]
    min_bundle                 = null
    mode                       = null
    poe_capable                = null
    poe_pre_standard_detection = null
    poe_status                 = null
    port_name                  = null
    port_number                = null
    port_owner                 = null
    port_prefix_type           = null
    port_security_policy       = null
    port_selection_criteria    = null
    qos_policy                 = null
    sample_direction           = null
    sflow_counter_interval     = null
    sflow_sample_rate          = null
    sflow_sampler              = null
    speed                      = null
    speed_mask                 = null
    stacking_port              = null
    status                     = null
    sticky_mac                 = null
    stp_bpdu_guard             = null
    stp_bpdu_guard_timeout     = null
    stp_root_guard             = null
    stp_state                  = null
    switch_id                  = null
    type                       = null
    untagged_vlans = [{
      vlan_name = null
    }]
    virtual_port = null
    vlan         = null
  }]

  static_mac = [{
    description = null
    id          = null
    interface   = null
    mac         = null
    type        = null
    vlan        = null
  }]

  storm_control = [{
    broadcast         = null
    local_override    = null
    rate              = null
    unknown_multicast = null
    unknown_unicast   = null
  }]

  stp_settings = [{
    forward_time   = null
    hello_time     = null
    local_override = null
    max_age        = null
    max_hops       = null
    name           = null
    pending_timer  = null
    revision       = null
    status         = null
  }]

  switch_log = [{
    local_override = null
    severity       = null
    status         = null
  }]

  switch_stp_settings = [{
    status = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "delayed_restart_trigger" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "directly_connected" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dynamic_capability" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dynamically_discovered" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fsw_wan1_admin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fsw_wan1_peer" {
  description = "(required)"
  type        = string
}

variable "fsw_wan2_admin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fsw_wan2_peer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_allowed_trunk_members" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner_vdom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "poe_pre_standard_detection" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pre_provisioned" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "staged_image_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switch_device_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "switch_id" {
  description = "(required)"
  type        = string
}

variable "switch_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "custom_command" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      command_entry = string
      command_name  = string
    }
  ))
  default = []
}

variable "igmp_snooping" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      aging_time              = number
      flood_unknown_multicast = string
      local_override          = string
    }
  ))
  default = []
}

variable "mirror" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dst  = string
      name = string
      src_egress = list(object(
        {
          name = string
        }
      ))
      src_ingress = list(object(
        {
          name = string
        }
      ))
      status           = string
      switching_packet = string
    }
  ))
  default = []
}

variable "n802_1x_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      link_down_auth     = string
      local_override     = string
      max_reauth_attempt = number
      reauth_period      = number
    }
  ))
  default = []
}

variable "ports" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allowed_vlans = list(object(
        {
          vlan_name = string
        }
      ))
      allowed_vlans_all         = string
      arp_inspection_trust      = string
      bundle                    = string
      description               = string
      dhcp_snoop_option82_trust = string
      dhcp_snooping             = string
      discard_mode              = string
      edge_port                 = string
      export_tags = list(object(
        {
          tag_name = string
        }
      ))
      export_to                  = string
      export_to_pool             = string
      export_to_pool_flag        = number
      fgt_peer_device_name       = string
      fgt_peer_port_name         = string
      fiber_port                 = number
      flags                      = number
      fortilink_port             = number
      igmp_snooping              = string
      igmps_flood_reports        = string
      igmps_flood_traffic        = string
      isl_local_trunk_name       = string
      isl_peer_device_name       = string
      isl_peer_port_name         = string
      lacp_speed                 = string
      learning_limit             = number
      lldp_profile               = string
      lldp_status                = string
      loop_guard                 = string
      loop_guard_timeout         = number
      max_bundle                 = number
      mclag                      = string
      member_withdrawal_behavior = string
      members = list(object(
        {
          member_name = string
        }
      ))
      min_bundle                 = number
      mode                       = string
      poe_capable                = number
      poe_pre_standard_detection = string
      poe_status                 = string
      port_name                  = string
      port_number                = number
      port_owner                 = string
      port_prefix_type           = number
      port_security_policy       = string
      port_selection_criteria    = string
      qos_policy                 = string
      sample_direction           = string
      sflow_counter_interval     = number
      sflow_sample_rate          = number
      sflow_sampler              = string
      speed                      = string
      speed_mask                 = number
      stacking_port              = number
      status                     = string
      sticky_mac                 = string
      stp_bpdu_guard             = string
      stp_bpdu_guard_timeout     = number
      stp_root_guard             = string
      stp_state                  = string
      switch_id                  = string
      type                       = string
      untagged_vlans = list(object(
        {
          vlan_name = string
        }
      ))
      virtual_port = number
      vlan         = string
    }
  ))
  default = []
}

variable "static_mac" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      description = string
      id          = number
      interface   = string
      mac         = string
      type        = string
      vlan        = string
    }
  ))
  default = []
}

variable "storm_control" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      broadcast         = string
      local_override    = string
      rate              = number
      unknown_multicast = string
      unknown_unicast   = string
    }
  ))
  default = []
}

variable "stp_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      forward_time   = number
      hello_time     = number
      local_override = string
      max_age        = number
      max_hops       = number
      name           = string
      pending_timer  = number
      revision       = number
      status         = string
    }
  ))
  default = []
}

variable "switch_log" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      local_override = string
      severity       = string
      status         = string
    }
  ))
  default = []
}

variable "switch_stp_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      status = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontroller_managedswitch" "this" {
  delayed_restart_trigger    = var.delayed_restart_trigger
  description                = var.description
  directly_connected         = var.directly_connected
  dynamic_capability         = var.dynamic_capability
  dynamically_discovered     = var.dynamically_discovered
  fsw_wan1_admin             = var.fsw_wan1_admin
  fsw_wan1_peer              = var.fsw_wan1_peer
  fsw_wan2_admin             = var.fsw_wan2_admin
  fsw_wan2_peer              = var.fsw_wan2_peer
  max_allowed_trunk_members  = var.max_allowed_trunk_members
  name                       = var.name
  owner_vdom                 = var.owner_vdom
  poe_pre_standard_detection = var.poe_pre_standard_detection
  pre_provisioned            = var.pre_provisioned
  staged_image_version       = var.staged_image_version
  switch_device_tag          = var.switch_device_tag
  switch_id                  = var.switch_id
  switch_profile             = var.switch_profile
  type                       = var.type
  version                    = var.version

  dynamic "custom_command" {
    for_each = var.custom_command
    content {
      command_entry = custom_command.value["command_entry"]
      command_name  = custom_command.value["command_name"]
    }
  }

  dynamic "igmp_snooping" {
    for_each = var.igmp_snooping
    content {
      aging_time              = igmp_snooping.value["aging_time"]
      flood_unknown_multicast = igmp_snooping.value["flood_unknown_multicast"]
      local_override          = igmp_snooping.value["local_override"]
    }
  }

  dynamic "mirror" {
    for_each = var.mirror
    content {
      dst              = mirror.value["dst"]
      name             = mirror.value["name"]
      status           = mirror.value["status"]
      switching_packet = mirror.value["switching_packet"]

      dynamic "src_egress" {
        for_each = mirror.value.src_egress
        content {
          name = src_egress.value["name"]
        }
      }

      dynamic "src_ingress" {
        for_each = mirror.value.src_ingress
        content {
          name = src_ingress.value["name"]
        }
      }

    }
  }

  dynamic "n802_1x_settings" {
    for_each = var.n802_1x_settings
    content {
      link_down_auth     = n802_1x_settings.value["link_down_auth"]
      local_override     = n802_1x_settings.value["local_override"]
      max_reauth_attempt = n802_1x_settings.value["max_reauth_attempt"]
      reauth_period      = n802_1x_settings.value["reauth_period"]
    }
  }

  dynamic "ports" {
    for_each = var.ports
    content {
      allowed_vlans_all          = ports.value["allowed_vlans_all"]
      arp_inspection_trust       = ports.value["arp_inspection_trust"]
      bundle                     = ports.value["bundle"]
      description                = ports.value["description"]
      dhcp_snoop_option82_trust  = ports.value["dhcp_snoop_option82_trust"]
      dhcp_snooping              = ports.value["dhcp_snooping"]
      discard_mode               = ports.value["discard_mode"]
      edge_port                  = ports.value["edge_port"]
      export_to                  = ports.value["export_to"]
      export_to_pool             = ports.value["export_to_pool"]
      export_to_pool_flag        = ports.value["export_to_pool_flag"]
      fgt_peer_device_name       = ports.value["fgt_peer_device_name"]
      fgt_peer_port_name         = ports.value["fgt_peer_port_name"]
      fiber_port                 = ports.value["fiber_port"]
      flags                      = ports.value["flags"]
      fortilink_port             = ports.value["fortilink_port"]
      igmp_snooping              = ports.value["igmp_snooping"]
      igmps_flood_reports        = ports.value["igmps_flood_reports"]
      igmps_flood_traffic        = ports.value["igmps_flood_traffic"]
      isl_local_trunk_name       = ports.value["isl_local_trunk_name"]
      isl_peer_device_name       = ports.value["isl_peer_device_name"]
      isl_peer_port_name         = ports.value["isl_peer_port_name"]
      lacp_speed                 = ports.value["lacp_speed"]
      learning_limit             = ports.value["learning_limit"]
      lldp_profile               = ports.value["lldp_profile"]
      lldp_status                = ports.value["lldp_status"]
      loop_guard                 = ports.value["loop_guard"]
      loop_guard_timeout         = ports.value["loop_guard_timeout"]
      max_bundle                 = ports.value["max_bundle"]
      mclag                      = ports.value["mclag"]
      member_withdrawal_behavior = ports.value["member_withdrawal_behavior"]
      min_bundle                 = ports.value["min_bundle"]
      mode                       = ports.value["mode"]
      poe_capable                = ports.value["poe_capable"]
      poe_pre_standard_detection = ports.value["poe_pre_standard_detection"]
      poe_status                 = ports.value["poe_status"]
      port_name                  = ports.value["port_name"]
      port_number                = ports.value["port_number"]
      port_owner                 = ports.value["port_owner"]
      port_prefix_type           = ports.value["port_prefix_type"]
      port_security_policy       = ports.value["port_security_policy"]
      port_selection_criteria    = ports.value["port_selection_criteria"]
      qos_policy                 = ports.value["qos_policy"]
      sample_direction           = ports.value["sample_direction"]
      sflow_counter_interval     = ports.value["sflow_counter_interval"]
      sflow_sample_rate          = ports.value["sflow_sample_rate"]
      sflow_sampler              = ports.value["sflow_sampler"]
      speed                      = ports.value["speed"]
      speed_mask                 = ports.value["speed_mask"]
      stacking_port              = ports.value["stacking_port"]
      status                     = ports.value["status"]
      sticky_mac                 = ports.value["sticky_mac"]
      stp_bpdu_guard             = ports.value["stp_bpdu_guard"]
      stp_bpdu_guard_timeout     = ports.value["stp_bpdu_guard_timeout"]
      stp_root_guard             = ports.value["stp_root_guard"]
      stp_state                  = ports.value["stp_state"]
      switch_id                  = ports.value["switch_id"]
      type                       = ports.value["type"]
      virtual_port               = ports.value["virtual_port"]
      vlan                       = ports.value["vlan"]

      dynamic "allowed_vlans" {
        for_each = ports.value.allowed_vlans
        content {
          vlan_name = allowed_vlans.value["vlan_name"]
        }
      }

      dynamic "export_tags" {
        for_each = ports.value.export_tags
        content {
          tag_name = export_tags.value["tag_name"]
        }
      }

      dynamic "members" {
        for_each = ports.value.members
        content {
          member_name = members.value["member_name"]
        }
      }

      dynamic "untagged_vlans" {
        for_each = ports.value.untagged_vlans
        content {
          vlan_name = untagged_vlans.value["vlan_name"]
        }
      }

    }
  }

  dynamic "static_mac" {
    for_each = var.static_mac
    content {
      description = static_mac.value["description"]
      id          = static_mac.value["id"]
      interface   = static_mac.value["interface"]
      mac         = static_mac.value["mac"]
      type        = static_mac.value["type"]
      vlan        = static_mac.value["vlan"]
    }
  }

  dynamic "storm_control" {
    for_each = var.storm_control
    content {
      broadcast         = storm_control.value["broadcast"]
      local_override    = storm_control.value["local_override"]
      rate              = storm_control.value["rate"]
      unknown_multicast = storm_control.value["unknown_multicast"]
      unknown_unicast   = storm_control.value["unknown_unicast"]
    }
  }

  dynamic "stp_settings" {
    for_each = var.stp_settings
    content {
      forward_time   = stp_settings.value["forward_time"]
      hello_time     = stp_settings.value["hello_time"]
      local_override = stp_settings.value["local_override"]
      max_age        = stp_settings.value["max_age"]
      max_hops       = stp_settings.value["max_hops"]
      name           = stp_settings.value["name"]
      pending_timer  = stp_settings.value["pending_timer"]
      revision       = stp_settings.value["revision"]
      status         = stp_settings.value["status"]
    }
  }

  dynamic "switch_log" {
    for_each = var.switch_log
    content {
      local_override = switch_log.value["local_override"]
      severity       = switch_log.value["severity"]
      status         = switch_log.value["status"]
    }
  }

  dynamic "switch_stp_settings" {
    for_each = var.switch_stp_settings
    content {
      status = switch_stp_settings.value["status"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "delayed_restart_trigger" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.delayed_restart_trigger
}

output "description" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.description
}

output "directly_connected" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.directly_connected
}

output "dynamic_capability" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.dynamic_capability
}

output "dynamically_discovered" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.dynamically_discovered
}

output "fsw_wan1_admin" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.fsw_wan1_admin
}

output "fsw_wan2_admin" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.fsw_wan2_admin
}

output "fsw_wan2_peer" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.fsw_wan2_peer
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.id
}

output "max_allowed_trunk_members" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.max_allowed_trunk_members
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.name
}

output "owner_vdom" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.owner_vdom
}

output "poe_pre_standard_detection" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.poe_pre_standard_detection
}

output "pre_provisioned" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.pre_provisioned
}

output "staged_image_version" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.staged_image_version
}

output "switch_device_tag" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.switch_device_tag
}

output "switch_profile" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.switch_profile
}

output "type" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.type
}

output "version" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.version
}

output "this" {
  value = fortios_switchcontroller_managedswitch.this
}
```

[top](#index)