# vsphere_distributed_port_group

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vsphere = ">= 1.25.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_distributed_port_group" {
  source = "./modules/vsphere/r/vsphere_distributed_port_group"

  # active_uplinks - (optional) is a type of list of string
  active_uplinks = []
  # allow_forged_transmits - (optional) is a type of bool
  allow_forged_transmits = null
  # allow_mac_changes - (optional) is a type of bool
  allow_mac_changes = null
  # allow_promiscuous - (optional) is a type of bool
  allow_promiscuous = null
  # auto_expand - (optional) is a type of bool
  auto_expand = null
  # block_all_ports - (optional) is a type of bool
  block_all_ports = null
  # block_override_allowed - (optional) is a type of bool
  block_override_allowed = null
  # check_beacon - (optional) is a type of bool
  check_beacon = null
  # custom_attributes - (optional) is a type of map of string
  custom_attributes = {}
  # description - (optional) is a type of string
  description = null
  # directpath_gen2_allowed - (optional) is a type of bool
  directpath_gen2_allowed = null
  # distributed_virtual_switch_uuid - (required) is a type of string
  distributed_virtual_switch_uuid = null
  # egress_shaping_average_bandwidth - (optional) is a type of number
  egress_shaping_average_bandwidth = null
  # egress_shaping_burst_size - (optional) is a type of number
  egress_shaping_burst_size = null
  # egress_shaping_enabled - (optional) is a type of bool
  egress_shaping_enabled = null
  # egress_shaping_peak_bandwidth - (optional) is a type of number
  egress_shaping_peak_bandwidth = null
  # failback - (optional) is a type of bool
  failback = null
  # ingress_shaping_average_bandwidth - (optional) is a type of number
  ingress_shaping_average_bandwidth = null
  # ingress_shaping_burst_size - (optional) is a type of number
  ingress_shaping_burst_size = null
  # ingress_shaping_enabled - (optional) is a type of bool
  ingress_shaping_enabled = null
  # ingress_shaping_peak_bandwidth - (optional) is a type of number
  ingress_shaping_peak_bandwidth = null
  # lacp_enabled - (optional) is a type of bool
  lacp_enabled = null
  # lacp_mode - (optional) is a type of string
  lacp_mode = null
  # live_port_moving_allowed - (optional) is a type of bool
  live_port_moving_allowed = null
  # name - (required) is a type of string
  name = null
  # netflow_enabled - (optional) is a type of bool
  netflow_enabled = null
  # netflow_override_allowed - (optional) is a type of bool
  netflow_override_allowed = null
  # network_resource_pool_key - (optional) is a type of string
  network_resource_pool_key = null
  # network_resource_pool_override_allowed - (optional) is a type of bool
  network_resource_pool_override_allowed = null
  # notify_switches - (optional) is a type of bool
  notify_switches = null
  # number_of_ports - (optional) is a type of number
  number_of_ports = null
  # port_config_reset_at_disconnect - (optional) is a type of bool
  port_config_reset_at_disconnect = null
  # port_name_format - (optional) is a type of string
  port_name_format = null
  # port_private_secondary_vlan_id - (optional) is a type of number
  port_private_secondary_vlan_id = null
  # security_policy_override_allowed - (optional) is a type of bool
  security_policy_override_allowed = null
  # shaping_override_allowed - (optional) is a type of bool
  shaping_override_allowed = null
  # standby_uplinks - (optional) is a type of list of string
  standby_uplinks = []
  # tags - (optional) is a type of set of string
  tags = []
  # teaming_policy - (optional) is a type of string
  teaming_policy = null
  # traffic_filter_override_allowed - (optional) is a type of bool
  traffic_filter_override_allowed = null
  # tx_uplink - (optional) is a type of bool
  tx_uplink = null
  # type - (optional) is a type of string
  type = null
  # uplink_teaming_override_allowed - (optional) is a type of bool
  uplink_teaming_override_allowed = null
  # vlan_id - (optional) is a type of number
  vlan_id = null
  # vlan_override_allowed - (optional) is a type of bool
  vlan_override_allowed = null

  vlan_range = [{
    max_vlan = null
    min_vlan = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "active_uplinks" {
  description = "(optional) - List of active uplinks used for load balancing, matching the names of the uplinks assigned in the DVS."
  type        = list(string)
  default     = null
}

variable "allow_forged_transmits" {
  description = "(optional) - Controls whether or not the virtual network adapter is allowed to send network traffic with a different MAC address than that of its own."
  type        = bool
  default     = null
}

variable "allow_mac_changes" {
  description = "(optional) - Controls whether or not the Media Access Control (MAC) address can be changed."
  type        = bool
  default     = null
}

variable "allow_promiscuous" {
  description = "(optional) - Enable promiscuous mode on the network. This flag indicates whether or not all traffic is seen on a given port."
  type        = bool
  default     = null
}

variable "auto_expand" {
  description = "(optional) - Auto-expands the port group beyond the port count configured in number_of_ports when necessary."
  type        = bool
  default     = null
}

variable "block_all_ports" {
  description = "(optional) - Indicates whether to block all ports by default."
  type        = bool
  default     = null
}

variable "block_override_allowed" {
  description = "(optional) - Allow the blocked setting of an individual port to override the setting in the portgroup."
  type        = bool
  default     = null
}

variable "check_beacon" {
  description = "(optional) - Enable beacon probing on the ports this policy applies to."
  type        = bool
  default     = null
}

variable "custom_attributes" {
  description = "(optional) - A list of custom attributes to set on this resource."
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional) - The description of the portgroup."
  type        = string
  default     = null
}

variable "directpath_gen2_allowed" {
  description = "(optional) - Allow VMDirectPath Gen2 on the ports this policy applies to."
  type        = bool
  default     = null
}

variable "distributed_virtual_switch_uuid" {
  description = "(required) - The UUID of the DVS to attach this port group to."
  type        = string
}

variable "egress_shaping_average_bandwidth" {
  description = "(optional) - The average egress bandwidth in bits per second if egress shaping is enabled on the port."
  type        = number
  default     = null
}

variable "egress_shaping_burst_size" {
  description = "(optional) - The maximum egress burst size allowed in bytes if egress shaping is enabled on the port."
  type        = number
  default     = null
}

variable "egress_shaping_enabled" {
  description = "(optional) - True if the traffic shaper is enabled for egress traffic on the port."
  type        = bool
  default     = null
}

variable "egress_shaping_peak_bandwidth" {
  description = "(optional) - The peak egress bandwidth during bursts in bits per second if egress traffic shaping is enabled on the port."
  type        = number
  default     = null
}

variable "failback" {
  description = "(optional) - If true, the teaming policy will re-activate failed interfaces higher in precedence when they come back up."
  type        = bool
  default     = null
}

variable "ingress_shaping_average_bandwidth" {
  description = "(optional) - The average ingress bandwidth in bits per second if ingress shaping is enabled on the port."
  type        = number
  default     = null
}

variable "ingress_shaping_burst_size" {
  description = "(optional) - The maximum ingress burst size allowed in bytes if ingress shaping is enabled on the port."
  type        = number
  default     = null
}

variable "ingress_shaping_enabled" {
  description = "(optional) - True if the traffic shaper is enabled for ingress traffic on the port."
  type        = bool
  default     = null
}

variable "ingress_shaping_peak_bandwidth" {
  description = "(optional) - The peak ingress bandwidth during bursts in bits per second if ingress traffic shaping is enabled on the port."
  type        = number
  default     = null
}

variable "lacp_enabled" {
  description = "(optional) - Whether or not to enable LACP on all uplink ports."
  type        = bool
  default     = null
}

variable "lacp_mode" {
  description = "(optional) - The uplink LACP mode to use. Can be one of active or passive."
  type        = string
  default     = null
}

variable "live_port_moving_allowed" {
  description = "(optional) - Allow a live port to be moved in and out of the portgroup."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - The name of the portgroup."
  type        = string
}

variable "netflow_enabled" {
  description = "(optional) - Indicates whether to enable netflow on all ports."
  type        = bool
  default     = null
}

variable "netflow_override_allowed" {
  description = "(optional) - Allow the enabling or disabling of Netflow on a port, contrary to the policy in the portgroup."
  type        = bool
  default     = null
}

variable "network_resource_pool_key" {
  description = "(optional) - The key of a network resource pool to associate with this portgroup."
  type        = string
  default     = null
}

variable "network_resource_pool_override_allowed" {
  description = "(optional) - Allow the network resource pool of an individual port to override the setting in the portgroup."
  type        = bool
  default     = null
}

variable "notify_switches" {
  description = "(optional) - If true, the teaming policy will notify the broadcast network of a NIC failover, triggering cache updates."
  type        = bool
  default     = null
}

variable "number_of_ports" {
  description = "(optional) - The number of ports in this portgroup. The DVS will expand and shrink by modifying this setting."
  type        = number
  default     = null
}

variable "port_config_reset_at_disconnect" {
  description = "(optional) - Reset the setting of any ports in this portgroup back to the default setting when the port disconnects."
  type        = bool
  default     = null
}

variable "port_name_format" {
  description = "(optional) - A template string to use when creating ports in the portgroup."
  type        = string
  default     = null
}

variable "port_private_secondary_vlan_id" {
  description = "(optional) - The secondary VLAN ID for this port."
  type        = number
  default     = null
}

variable "security_policy_override_allowed" {
  description = "(optional) - Allow security policy settings on a port to override those on the portgroup."
  type        = bool
  default     = null
}

variable "shaping_override_allowed" {
  description = "(optional) - Allow the traffic shaping policies of an individual port to override the settings in the portgroup."
  type        = bool
  default     = null
}

variable "standby_uplinks" {
  description = "(optional) - List of standby uplinks used for load balancing, matching the names of the uplinks assigned in the DVS."
  type        = list(string)
  default     = null
}

variable "tags" {
  description = "(optional) - A list of tag IDs to apply to this object."
  type        = set(string)
  default     = null
}

variable "teaming_policy" {
  description = "(optional) - The network adapter teaming policy. Can be one of loadbalance_ip, loadbalance_srcmac, loadbalance_srcid, failover_explicit, or loadbalance_loadbased."
  type        = string
  default     = null
}

variable "traffic_filter_override_allowed" {
  description = "(optional) - Allow any filter policies set on the individual port to override those in the portgroup."
  type        = bool
  default     = null
}

variable "tx_uplink" {
  description = "(optional) - If true, a copy of packets sent to the switch will always be forwarded to an uplink in addition to the regular packet forwarded done by the switch."
  type        = bool
  default     = null
}

variable "type" {
  description = "(optional) - The type of portgroup. Can be one of earlyBinding (static) or ephemeral."
  type        = string
  default     = null
}

variable "uplink_teaming_override_allowed" {
  description = "(optional) - Allow the uplink teaming policies on a port to override those on the portgroup."
  type        = bool
  default     = null
}

variable "vlan_id" {
  description = "(optional) - The VLAN ID for single VLAN mode. 0 denotes no VLAN."
  type        = number
  default     = null
}

variable "vlan_override_allowed" {
  description = "(optional) - Allow the VLAN configuration on a port to override those on the portgroup."
  type        = bool
  default     = null
}

variable "vlan_range" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      max_vlan = number
      min_vlan = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_distributed_port_group" "this" {
  # active_uplinks - (optional) is a type of list of string
  active_uplinks = var.active_uplinks
  # allow_forged_transmits - (optional) is a type of bool
  allow_forged_transmits = var.allow_forged_transmits
  # allow_mac_changes - (optional) is a type of bool
  allow_mac_changes = var.allow_mac_changes
  # allow_promiscuous - (optional) is a type of bool
  allow_promiscuous = var.allow_promiscuous
  # auto_expand - (optional) is a type of bool
  auto_expand = var.auto_expand
  # block_all_ports - (optional) is a type of bool
  block_all_ports = var.block_all_ports
  # block_override_allowed - (optional) is a type of bool
  block_override_allowed = var.block_override_allowed
  # check_beacon - (optional) is a type of bool
  check_beacon = var.check_beacon
  # custom_attributes - (optional) is a type of map of string
  custom_attributes = var.custom_attributes
  # description - (optional) is a type of string
  description = var.description
  # directpath_gen2_allowed - (optional) is a type of bool
  directpath_gen2_allowed = var.directpath_gen2_allowed
  # distributed_virtual_switch_uuid - (required) is a type of string
  distributed_virtual_switch_uuid = var.distributed_virtual_switch_uuid
  # egress_shaping_average_bandwidth - (optional) is a type of number
  egress_shaping_average_bandwidth = var.egress_shaping_average_bandwidth
  # egress_shaping_burst_size - (optional) is a type of number
  egress_shaping_burst_size = var.egress_shaping_burst_size
  # egress_shaping_enabled - (optional) is a type of bool
  egress_shaping_enabled = var.egress_shaping_enabled
  # egress_shaping_peak_bandwidth - (optional) is a type of number
  egress_shaping_peak_bandwidth = var.egress_shaping_peak_bandwidth
  # failback - (optional) is a type of bool
  failback = var.failback
  # ingress_shaping_average_bandwidth - (optional) is a type of number
  ingress_shaping_average_bandwidth = var.ingress_shaping_average_bandwidth
  # ingress_shaping_burst_size - (optional) is a type of number
  ingress_shaping_burst_size = var.ingress_shaping_burst_size
  # ingress_shaping_enabled - (optional) is a type of bool
  ingress_shaping_enabled = var.ingress_shaping_enabled
  # ingress_shaping_peak_bandwidth - (optional) is a type of number
  ingress_shaping_peak_bandwidth = var.ingress_shaping_peak_bandwidth
  # lacp_enabled - (optional) is a type of bool
  lacp_enabled = var.lacp_enabled
  # lacp_mode - (optional) is a type of string
  lacp_mode = var.lacp_mode
  # live_port_moving_allowed - (optional) is a type of bool
  live_port_moving_allowed = var.live_port_moving_allowed
  # name - (required) is a type of string
  name = var.name
  # netflow_enabled - (optional) is a type of bool
  netflow_enabled = var.netflow_enabled
  # netflow_override_allowed - (optional) is a type of bool
  netflow_override_allowed = var.netflow_override_allowed
  # network_resource_pool_key - (optional) is a type of string
  network_resource_pool_key = var.network_resource_pool_key
  # network_resource_pool_override_allowed - (optional) is a type of bool
  network_resource_pool_override_allowed = var.network_resource_pool_override_allowed
  # notify_switches - (optional) is a type of bool
  notify_switches = var.notify_switches
  # number_of_ports - (optional) is a type of number
  number_of_ports = var.number_of_ports
  # port_config_reset_at_disconnect - (optional) is a type of bool
  port_config_reset_at_disconnect = var.port_config_reset_at_disconnect
  # port_name_format - (optional) is a type of string
  port_name_format = var.port_name_format
  # port_private_secondary_vlan_id - (optional) is a type of number
  port_private_secondary_vlan_id = var.port_private_secondary_vlan_id
  # security_policy_override_allowed - (optional) is a type of bool
  security_policy_override_allowed = var.security_policy_override_allowed
  # shaping_override_allowed - (optional) is a type of bool
  shaping_override_allowed = var.shaping_override_allowed
  # standby_uplinks - (optional) is a type of list of string
  standby_uplinks = var.standby_uplinks
  # tags - (optional) is a type of set of string
  tags = var.tags
  # teaming_policy - (optional) is a type of string
  teaming_policy = var.teaming_policy
  # traffic_filter_override_allowed - (optional) is a type of bool
  traffic_filter_override_allowed = var.traffic_filter_override_allowed
  # tx_uplink - (optional) is a type of bool
  tx_uplink = var.tx_uplink
  # type - (optional) is a type of string
  type = var.type
  # uplink_teaming_override_allowed - (optional) is a type of bool
  uplink_teaming_override_allowed = var.uplink_teaming_override_allowed
  # vlan_id - (optional) is a type of number
  vlan_id = var.vlan_id
  # vlan_override_allowed - (optional) is a type of bool
  vlan_override_allowed = var.vlan_override_allowed

  dynamic "vlan_range" {
    for_each = var.vlan_range
    content {
      # max_vlan - (required) is a type of number
      max_vlan = vlan_range.value["max_vlan"]
      # min_vlan - (required) is a type of number
      min_vlan = vlan_range.value["min_vlan"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "active_uplinks" {
  description = "returns a list of string"
  value       = vsphere_distributed_port_group.this.active_uplinks
}

output "allow_forged_transmits" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.allow_forged_transmits
}

output "allow_mac_changes" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.allow_mac_changes
}

output "allow_promiscuous" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.allow_promiscuous
}

output "block_all_ports" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.block_all_ports
}

output "check_beacon" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.check_beacon
}

output "config_version" {
  description = "returns a string"
  value       = vsphere_distributed_port_group.this.config_version
}

output "directpath_gen2_allowed" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.directpath_gen2_allowed
}

output "egress_shaping_average_bandwidth" {
  description = "returns a number"
  value       = vsphere_distributed_port_group.this.egress_shaping_average_bandwidth
}

output "egress_shaping_burst_size" {
  description = "returns a number"
  value       = vsphere_distributed_port_group.this.egress_shaping_burst_size
}

output "egress_shaping_enabled" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.egress_shaping_enabled
}

output "egress_shaping_peak_bandwidth" {
  description = "returns a number"
  value       = vsphere_distributed_port_group.this.egress_shaping_peak_bandwidth
}

output "failback" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.failback
}

output "id" {
  description = "returns a string"
  value       = vsphere_distributed_port_group.this.id
}

output "ingress_shaping_average_bandwidth" {
  description = "returns a number"
  value       = vsphere_distributed_port_group.this.ingress_shaping_average_bandwidth
}

output "ingress_shaping_burst_size" {
  description = "returns a number"
  value       = vsphere_distributed_port_group.this.ingress_shaping_burst_size
}

output "ingress_shaping_enabled" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.ingress_shaping_enabled
}

output "ingress_shaping_peak_bandwidth" {
  description = "returns a number"
  value       = vsphere_distributed_port_group.this.ingress_shaping_peak_bandwidth
}

output "key" {
  description = "returns a string"
  value       = vsphere_distributed_port_group.this.key
}

output "lacp_enabled" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.lacp_enabled
}

output "lacp_mode" {
  description = "returns a string"
  value       = vsphere_distributed_port_group.this.lacp_mode
}

output "netflow_enabled" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.netflow_enabled
}

output "notify_switches" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.notify_switches
}

output "number_of_ports" {
  description = "returns a number"
  value       = vsphere_distributed_port_group.this.number_of_ports
}

output "port_private_secondary_vlan_id" {
  description = "returns a number"
  value       = vsphere_distributed_port_group.this.port_private_secondary_vlan_id
}

output "standby_uplinks" {
  description = "returns a list of string"
  value       = vsphere_distributed_port_group.this.standby_uplinks
}

output "teaming_policy" {
  description = "returns a string"
  value       = vsphere_distributed_port_group.this.teaming_policy
}

output "tx_uplink" {
  description = "returns a bool"
  value       = vsphere_distributed_port_group.this.tx_uplink
}

output "vlan_id" {
  description = "returns a number"
  value       = vsphere_distributed_port_group.this.vlan_id
}

output "this" {
  value = vsphere_distributed_port_group.this
}
```

[top](#index)