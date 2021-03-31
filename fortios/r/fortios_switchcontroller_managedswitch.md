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
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_switchcontroller_managedswitch" {
  source = "./modules/fortios/r/fortios_switchcontroller_managedswitch"

  # access_profile - (optional) is a type of string
  access_profile = null
  # delayed_restart_trigger - (optional) is a type of number
  delayed_restart_trigger = null
  # description - (optional) is a type of string
  description = null
  # directly_connected - (optional) is a type of number
  directly_connected = null
  # dynamic_capability - (optional) is a type of number
  dynamic_capability = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # dynamically_discovered - (optional) is a type of number
  dynamically_discovered = null
  # firmware_provision - (optional) is a type of string
  firmware_provision = null
  # firmware_provision_version - (optional) is a type of string
  firmware_provision_version = null
  # flow_identity - (optional) is a type of string
  flow_identity = null
  # fsw_wan1_admin - (optional) is a type of string
  fsw_wan1_admin = null
  # fsw_wan1_peer - (required) is a type of string
  fsw_wan1_peer = null
  # fsw_wan2_admin - (optional) is a type of string
  fsw_wan2_admin = null
  # fsw_wan2_peer - (optional) is a type of string
  fsw_wan2_peer = null
  # l3_discovered - (optional) is a type of number
  l3_discovered = null
  # max_allowed_trunk_members - (optional) is a type of number
  max_allowed_trunk_members = null
  # mclag_igmp_snooping_aware - (optional) is a type of string
  mclag_igmp_snooping_aware = null
  # name - (optional) is a type of string
  name = null
  # override_snmp_community - (optional) is a type of string
  override_snmp_community = null
  # override_snmp_sysinfo - (optional) is a type of string
  override_snmp_sysinfo = null
  # override_snmp_trap_threshold - (optional) is a type of string
  override_snmp_trap_threshold = null
  # override_snmp_user - (optional) is a type of string
  override_snmp_user = null
  # owner_vdom - (optional) is a type of string
  owner_vdom = null
  # poe_detection_type - (optional) is a type of number
  poe_detection_type = null
  # poe_lldp_detection - (optional) is a type of string
  poe_lldp_detection = null
  # poe_pre_standard_detection - (optional) is a type of string
  poe_pre_standard_detection = null
  # pre_provisioned - (optional) is a type of number
  pre_provisioned = null
  # qos_drop_policy - (optional) is a type of string
  qos_drop_policy = null
  # qos_red_probability - (optional) is a type of number
  qos_red_probability = null
  # staged_image_version - (optional) is a type of string
  staged_image_version = null
  # switch_device_tag - (optional) is a type of string
  switch_device_tag = null
  # switch_dhcp_opt43_key - (optional) is a type of string
  switch_dhcp_opt43_key = null
  # switch_id - (required) is a type of string
  switch_id = null
  # switch_profile - (optional) is a type of string
  switch_profile = null
  # tdr_supported - (optional) is a type of string
  tdr_supported = null
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

  ip_source_guard = [{
    binding_entry = [{
      entry_name = null
      ip         = null
      mac        = null
    }]
    description = null
    port        = null
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
    tx_period          = null
  }]

  ports = [{
    access_mode     = null
    aggregator_mode = null
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
    fec_capable                = null
    fec_state                  = null
    fgt_peer_device_name       = null
    fgt_peer_port_name         = null
    fiber_port                 = null
    flags                      = null
    flow_control               = null
    fortilink_port             = null
    igmp_snooping              = null
    igmps_flood_reports        = null
    igmps_flood_traffic        = null
    ip_source_guard            = null
    isl_local_trunk_name       = null
    isl_peer_device_name       = null
    isl_peer_port_name         = null
    lacp_speed                 = null
    learning_limit             = null
    lldp_profile               = null
    lldp_status                = null
    loop_guard                 = null
    loop_guard_timeout         = null
    mac_addr                   = null
    max_bundle                 = null
    mclag                      = null
    mclag_icl_port             = null
    media_type                 = null
    member_withdrawal_behavior = null
    members = [{
      member_name = null
    }]
    min_bundle                 = null
    mode                       = null
    p2p_port                   = null
    packet_sample_rate         = null
    packet_sampler             = null
    pause_meter                = null
    pause_meter_resume         = null
    poe_capable                = null
    poe_pre_standard_detection = null
    poe_status                 = null
    port_name                  = null
    port_number                = null
    port_owner                 = null
    port_prefix_type           = null
    port_security_policy       = null
    port_selection_criteria    = null
    ptp_policy                 = null
    qos_policy                 = null
    rpvst_port                 = null
    sample_direction           = null
    sflow_counter_interval     = null
    sflow_sample_rate          = null
    sflow_sampler              = null
    speed                      = null
    speed_mask                 = null
    stacking_port              = null
    status                     = null
    sticky_mac                 = null
    storm_control_policy       = null
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

  remote_log = [{
    csv      = null
    facility = null
    name     = null
    port     = null
    server   = null
    severity = null
    status   = null
  }]

  snmp_community = [{
    events = null
    hosts = [{
      id = null
      ip = null
    }]
    id               = null
    name             = null
    query_v1_port    = null
    query_v1_status  = null
    query_v2c_port   = null
    query_v2c_status = null
    status           = null
    trap_v1_lport    = null
    trap_v1_rport    = null
    trap_v1_status   = null
    trap_v2c_lport   = null
    trap_v2c_rport   = null
    trap_v2c_status  = null
  }]

  snmp_sysinfo = [{
    contact_info = null
    description  = null
    engine_id    = null
    location     = null
    status       = null
  }]

  snmp_trap_threshold = [{
    trap_high_cpu_threshold   = null
    trap_log_full_threshold   = null
    trap_low_memory_threshold = null
  }]

  snmp_user = [{
    auth_proto     = null
    auth_pwd       = null
    name           = null
    priv_proto     = null
    priv_pwd       = null
    queries        = null
    query_port     = null
    security_level = null
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

  stp_instance = [{
    id       = null
    priority = null
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
variable "access_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamically_discovered" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "firmware_provision" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firmware_provision_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flow_identity" {
  description = "(optional)"
  type        = string
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

variable "l3_discovered" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_allowed_trunk_members" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "mclag_igmp_snooping_aware" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_snmp_community" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_snmp_sysinfo" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_snmp_trap_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_snmp_user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner_vdom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "poe_detection_type" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "poe_lldp_detection" {
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

variable "qos_drop_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "qos_red_probability" {
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

variable "switch_dhcp_opt43_key" {
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

variable "tdr_supported" {
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

variable "ip_source_guard" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      binding_entry = list(object(
        {
          entry_name = string
          ip         = string
          mac        = string
        }
      ))
      description = string
      port        = string
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
      tx_period          = number
    }
  ))
  default = []
}

variable "ports" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_mode     = string
      aggregator_mode = string
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
      fec_capable                = number
      fec_state                  = string
      fgt_peer_device_name       = string
      fgt_peer_port_name         = string
      fiber_port                 = number
      flags                      = number
      flow_control               = string
      fortilink_port             = number
      igmp_snooping              = string
      igmps_flood_reports        = string
      igmps_flood_traffic        = string
      ip_source_guard            = string
      isl_local_trunk_name       = string
      isl_peer_device_name       = string
      isl_peer_port_name         = string
      lacp_speed                 = string
      learning_limit             = number
      lldp_profile               = string
      lldp_status                = string
      loop_guard                 = string
      loop_guard_timeout         = number
      mac_addr                   = string
      max_bundle                 = number
      mclag                      = string
      mclag_icl_port             = number
      media_type                 = string
      member_withdrawal_behavior = string
      members = list(object(
        {
          member_name = string
        }
      ))
      min_bundle                 = number
      mode                       = string
      p2p_port                   = number
      packet_sample_rate         = number
      packet_sampler             = string
      pause_meter                = number
      pause_meter_resume         = string
      poe_capable                = number
      poe_pre_standard_detection = string
      poe_status                 = string
      port_name                  = string
      port_number                = number
      port_owner                 = string
      port_prefix_type           = number
      port_security_policy       = string
      port_selection_criteria    = string
      ptp_policy                 = string
      qos_policy                 = string
      rpvst_port                 = string
      sample_direction           = string
      sflow_counter_interval     = number
      sflow_sample_rate          = number
      sflow_sampler              = string
      speed                      = string
      speed_mask                 = number
      stacking_port              = number
      status                     = string
      sticky_mac                 = string
      storm_control_policy       = string
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

variable "remote_log" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      csv      = string
      facility = string
      name     = string
      port     = number
      server   = string
      severity = string
      status   = string
    }
  ))
  default = []
}

variable "snmp_community" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      events = string
      hosts = list(object(
        {
          id = number
          ip = string
        }
      ))
      id               = number
      name             = string
      query_v1_port    = number
      query_v1_status  = string
      query_v2c_port   = number
      query_v2c_status = string
      status           = string
      trap_v1_lport    = number
      trap_v1_rport    = number
      trap_v1_status   = string
      trap_v2c_lport   = number
      trap_v2c_rport   = number
      trap_v2c_status  = string
    }
  ))
  default = []
}

variable "snmp_sysinfo" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      contact_info = string
      description  = string
      engine_id    = string
      location     = string
      status       = string
    }
  ))
  default = []
}

variable "snmp_trap_threshold" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      trap_high_cpu_threshold   = number
      trap_log_full_threshold   = number
      trap_low_memory_threshold = number
    }
  ))
  default = []
}

variable "snmp_user" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auth_proto     = string
      auth_pwd       = string
      name           = string
      priv_proto     = string
      priv_pwd       = string
      queries        = string
      query_port     = number
      security_level = string
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

variable "stp_instance" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      id       = string
      priority = string
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
  access_profile               = var.access_profile
  delayed_restart_trigger      = var.delayed_restart_trigger
  description                  = var.description
  directly_connected           = var.directly_connected
  dynamic_capability           = var.dynamic_capability
  dynamic_sort_subtable        = var.dynamic_sort_subtable
  dynamically_discovered       = var.dynamically_discovered
  firmware_provision           = var.firmware_provision
  firmware_provision_version   = var.firmware_provision_version
  flow_identity                = var.flow_identity
  fsw_wan1_admin               = var.fsw_wan1_admin
  fsw_wan1_peer                = var.fsw_wan1_peer
  fsw_wan2_admin               = var.fsw_wan2_admin
  fsw_wan2_peer                = var.fsw_wan2_peer
  l3_discovered                = var.l3_discovered
  max_allowed_trunk_members    = var.max_allowed_trunk_members
  mclag_igmp_snooping_aware    = var.mclag_igmp_snooping_aware
  name                         = var.name
  override_snmp_community      = var.override_snmp_community
  override_snmp_sysinfo        = var.override_snmp_sysinfo
  override_snmp_trap_threshold = var.override_snmp_trap_threshold
  override_snmp_user           = var.override_snmp_user
  owner_vdom                   = var.owner_vdom
  poe_detection_type           = var.poe_detection_type
  poe_lldp_detection           = var.poe_lldp_detection
  poe_pre_standard_detection   = var.poe_pre_standard_detection
  pre_provisioned              = var.pre_provisioned
  qos_drop_policy              = var.qos_drop_policy
  qos_red_probability          = var.qos_red_probability
  staged_image_version         = var.staged_image_version
  switch_device_tag            = var.switch_device_tag
  switch_dhcp_opt43_key        = var.switch_dhcp_opt43_key
  switch_id                    = var.switch_id
  switch_profile               = var.switch_profile
  tdr_supported                = var.tdr_supported
  type                         = var.type
  version                      = var.version

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

  dynamic "ip_source_guard" {
    for_each = var.ip_source_guard
    content {
      description = ip_source_guard.value["description"]
      port        = ip_source_guard.value["port"]

      dynamic "binding_entry" {
        for_each = ip_source_guard.value.binding_entry
        content {
          entry_name = binding_entry.value["entry_name"]
          ip         = binding_entry.value["ip"]
          mac        = binding_entry.value["mac"]
        }
      }

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
      tx_period          = n802_1x_settings.value["tx_period"]
    }
  }

  dynamic "ports" {
    for_each = var.ports
    content {
      access_mode                = ports.value["access_mode"]
      aggregator_mode            = ports.value["aggregator_mode"]
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
      fec_capable                = ports.value["fec_capable"]
      fec_state                  = ports.value["fec_state"]
      fgt_peer_device_name       = ports.value["fgt_peer_device_name"]
      fgt_peer_port_name         = ports.value["fgt_peer_port_name"]
      fiber_port                 = ports.value["fiber_port"]
      flags                      = ports.value["flags"]
      flow_control               = ports.value["flow_control"]
      fortilink_port             = ports.value["fortilink_port"]
      igmp_snooping              = ports.value["igmp_snooping"]
      igmps_flood_reports        = ports.value["igmps_flood_reports"]
      igmps_flood_traffic        = ports.value["igmps_flood_traffic"]
      ip_source_guard            = ports.value["ip_source_guard"]
      isl_local_trunk_name       = ports.value["isl_local_trunk_name"]
      isl_peer_device_name       = ports.value["isl_peer_device_name"]
      isl_peer_port_name         = ports.value["isl_peer_port_name"]
      lacp_speed                 = ports.value["lacp_speed"]
      learning_limit             = ports.value["learning_limit"]
      lldp_profile               = ports.value["lldp_profile"]
      lldp_status                = ports.value["lldp_status"]
      loop_guard                 = ports.value["loop_guard"]
      loop_guard_timeout         = ports.value["loop_guard_timeout"]
      mac_addr                   = ports.value["mac_addr"]
      max_bundle                 = ports.value["max_bundle"]
      mclag                      = ports.value["mclag"]
      mclag_icl_port             = ports.value["mclag_icl_port"]
      media_type                 = ports.value["media_type"]
      member_withdrawal_behavior = ports.value["member_withdrawal_behavior"]
      min_bundle                 = ports.value["min_bundle"]
      mode                       = ports.value["mode"]
      p2p_port                   = ports.value["p2p_port"]
      packet_sample_rate         = ports.value["packet_sample_rate"]
      packet_sampler             = ports.value["packet_sampler"]
      pause_meter                = ports.value["pause_meter"]
      pause_meter_resume         = ports.value["pause_meter_resume"]
      poe_capable                = ports.value["poe_capable"]
      poe_pre_standard_detection = ports.value["poe_pre_standard_detection"]
      poe_status                 = ports.value["poe_status"]
      port_name                  = ports.value["port_name"]
      port_number                = ports.value["port_number"]
      port_owner                 = ports.value["port_owner"]
      port_prefix_type           = ports.value["port_prefix_type"]
      port_security_policy       = ports.value["port_security_policy"]
      port_selection_criteria    = ports.value["port_selection_criteria"]
      ptp_policy                 = ports.value["ptp_policy"]
      qos_policy                 = ports.value["qos_policy"]
      rpvst_port                 = ports.value["rpvst_port"]
      sample_direction           = ports.value["sample_direction"]
      sflow_counter_interval     = ports.value["sflow_counter_interval"]
      sflow_sample_rate          = ports.value["sflow_sample_rate"]
      sflow_sampler              = ports.value["sflow_sampler"]
      speed                      = ports.value["speed"]
      speed_mask                 = ports.value["speed_mask"]
      stacking_port              = ports.value["stacking_port"]
      status                     = ports.value["status"]
      sticky_mac                 = ports.value["sticky_mac"]
      storm_control_policy       = ports.value["storm_control_policy"]
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

  dynamic "remote_log" {
    for_each = var.remote_log
    content {
      csv      = remote_log.value["csv"]
      facility = remote_log.value["facility"]
      name     = remote_log.value["name"]
      port     = remote_log.value["port"]
      server   = remote_log.value["server"]
      severity = remote_log.value["severity"]
      status   = remote_log.value["status"]
    }
  }

  dynamic "snmp_community" {
    for_each = var.snmp_community
    content {
      events           = snmp_community.value["events"]
      id               = snmp_community.value["id"]
      name             = snmp_community.value["name"]
      query_v1_port    = snmp_community.value["query_v1_port"]
      query_v1_status  = snmp_community.value["query_v1_status"]
      query_v2c_port   = snmp_community.value["query_v2c_port"]
      query_v2c_status = snmp_community.value["query_v2c_status"]
      status           = snmp_community.value["status"]
      trap_v1_lport    = snmp_community.value["trap_v1_lport"]
      trap_v1_rport    = snmp_community.value["trap_v1_rport"]
      trap_v1_status   = snmp_community.value["trap_v1_status"]
      trap_v2c_lport   = snmp_community.value["trap_v2c_lport"]
      trap_v2c_rport   = snmp_community.value["trap_v2c_rport"]
      trap_v2c_status  = snmp_community.value["trap_v2c_status"]

      dynamic "hosts" {
        for_each = snmp_community.value.hosts
        content {
          id = hosts.value["id"]
          ip = hosts.value["ip"]
        }
      }

    }
  }

  dynamic "snmp_sysinfo" {
    for_each = var.snmp_sysinfo
    content {
      contact_info = snmp_sysinfo.value["contact_info"]
      description  = snmp_sysinfo.value["description"]
      engine_id    = snmp_sysinfo.value["engine_id"]
      location     = snmp_sysinfo.value["location"]
      status       = snmp_sysinfo.value["status"]
    }
  }

  dynamic "snmp_trap_threshold" {
    for_each = var.snmp_trap_threshold
    content {
      trap_high_cpu_threshold   = snmp_trap_threshold.value["trap_high_cpu_threshold"]
      trap_log_full_threshold   = snmp_trap_threshold.value["trap_log_full_threshold"]
      trap_low_memory_threshold = snmp_trap_threshold.value["trap_low_memory_threshold"]
    }
  }

  dynamic "snmp_user" {
    for_each = var.snmp_user
    content {
      auth_proto     = snmp_user.value["auth_proto"]
      auth_pwd       = snmp_user.value["auth_pwd"]
      name           = snmp_user.value["name"]
      priv_proto     = snmp_user.value["priv_proto"]
      priv_pwd       = snmp_user.value["priv_pwd"]
      queries        = snmp_user.value["queries"]
      query_port     = snmp_user.value["query_port"]
      security_level = snmp_user.value["security_level"]
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

  dynamic "stp_instance" {
    for_each = var.stp_instance
    content {
      id       = stp_instance.value["id"]
      priority = stp_instance.value["priority"]
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
output "access_profile" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.access_profile
}

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

output "firmware_provision" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.firmware_provision
}

output "firmware_provision_version" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.firmware_provision_version
}

output "flow_identity" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.flow_identity
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

output "l3_discovered" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.l3_discovered
}

output "max_allowed_trunk_members" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.max_allowed_trunk_members
}

output "mclag_igmp_snooping_aware" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.mclag_igmp_snooping_aware
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.name
}

output "override_snmp_community" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.override_snmp_community
}

output "override_snmp_sysinfo" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.override_snmp_sysinfo
}

output "override_snmp_trap_threshold" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.override_snmp_trap_threshold
}

output "override_snmp_user" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.override_snmp_user
}

output "owner_vdom" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.owner_vdom
}

output "poe_detection_type" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.poe_detection_type
}

output "poe_lldp_detection" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.poe_lldp_detection
}

output "poe_pre_standard_detection" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.poe_pre_standard_detection
}

output "pre_provisioned" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.pre_provisioned
}

output "qos_drop_policy" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.qos_drop_policy
}

output "qos_red_probability" {
  description = "returns a number"
  value       = fortios_switchcontroller_managedswitch.this.qos_red_probability
}

output "staged_image_version" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.staged_image_version
}

output "switch_device_tag" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.switch_device_tag
}

output "switch_dhcp_opt43_key" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.switch_dhcp_opt43_key
}

output "switch_profile" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.switch_profile
}

output "tdr_supported" {
  description = "returns a string"
  value       = fortios_switchcontroller_managedswitch.this.tdr_supported
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