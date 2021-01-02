# vsphere_distributed_virtual_switch

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
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vsphere_distributed_virtual_switch" {
  source = "./modules/vsphere/r/vsphere_distributed_virtual_switch"

  # active_uplinks - (optional) is a type of list of string
  active_uplinks = []
  # allow_forged_transmits - (optional) is a type of bool
  allow_forged_transmits = null
  # allow_mac_changes - (optional) is a type of bool
  allow_mac_changes = null
  # allow_promiscuous - (optional) is a type of bool
  allow_promiscuous = null
  # block_all_ports - (optional) is a type of bool
  block_all_ports = null
  # check_beacon - (optional) is a type of bool
  check_beacon = null
  # contact_detail - (optional) is a type of string
  contact_detail = null
  # contact_name - (optional) is a type of string
  contact_name = null
  # custom_attributes - (optional) is a type of map of string
  custom_attributes = {}
  # datacenter_id - (required) is a type of string
  datacenter_id = null
  # description - (optional) is a type of string
  description = null
  # directpath_gen2_allowed - (optional) is a type of bool
  directpath_gen2_allowed = null
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
  # faulttolerance_maximum_mbit - (optional) is a type of number
  faulttolerance_maximum_mbit = null
  # faulttolerance_reservation_mbit - (optional) is a type of number
  faulttolerance_reservation_mbit = null
  # faulttolerance_share_count - (optional) is a type of number
  faulttolerance_share_count = null
  # faulttolerance_share_level - (optional) is a type of string
  faulttolerance_share_level = null
  # folder - (optional) is a type of string
  folder = null
  # hbr_maximum_mbit - (optional) is a type of number
  hbr_maximum_mbit = null
  # hbr_reservation_mbit - (optional) is a type of number
  hbr_reservation_mbit = null
  # hbr_share_count - (optional) is a type of number
  hbr_share_count = null
  # hbr_share_level - (optional) is a type of string
  hbr_share_level = null
  # ignore_other_pvlan_mappings - (optional) is a type of bool
  ignore_other_pvlan_mappings = null
  # ingress_shaping_average_bandwidth - (optional) is a type of number
  ingress_shaping_average_bandwidth = null
  # ingress_shaping_burst_size - (optional) is a type of number
  ingress_shaping_burst_size = null
  # ingress_shaping_enabled - (optional) is a type of bool
  ingress_shaping_enabled = null
  # ingress_shaping_peak_bandwidth - (optional) is a type of number
  ingress_shaping_peak_bandwidth = null
  # ipv4_address - (optional) is a type of string
  ipv4_address = null
  # iscsi_maximum_mbit - (optional) is a type of number
  iscsi_maximum_mbit = null
  # iscsi_reservation_mbit - (optional) is a type of number
  iscsi_reservation_mbit = null
  # iscsi_share_count - (optional) is a type of number
  iscsi_share_count = null
  # iscsi_share_level - (optional) is a type of string
  iscsi_share_level = null
  # lacp_api_version - (optional) is a type of string
  lacp_api_version = null
  # lacp_enabled - (optional) is a type of bool
  lacp_enabled = null
  # lacp_mode - (optional) is a type of string
  lacp_mode = null
  # link_discovery_operation - (optional) is a type of string
  link_discovery_operation = null
  # link_discovery_protocol - (optional) is a type of string
  link_discovery_protocol = null
  # management_maximum_mbit - (optional) is a type of number
  management_maximum_mbit = null
  # management_reservation_mbit - (optional) is a type of number
  management_reservation_mbit = null
  # management_share_count - (optional) is a type of number
  management_share_count = null
  # management_share_level - (optional) is a type of string
  management_share_level = null
  # max_mtu - (optional) is a type of number
  max_mtu = null
  # multicast_filtering_mode - (optional) is a type of string
  multicast_filtering_mode = null
  # name - (required) is a type of string
  name = null
  # netflow_active_flow_timeout - (optional) is a type of number
  netflow_active_flow_timeout = null
  # netflow_collector_ip_address - (optional) is a type of string
  netflow_collector_ip_address = null
  # netflow_collector_port - (optional) is a type of number
  netflow_collector_port = null
  # netflow_enabled - (optional) is a type of bool
  netflow_enabled = null
  # netflow_idle_flow_timeout - (optional) is a type of number
  netflow_idle_flow_timeout = null
  # netflow_internal_flows_only - (optional) is a type of bool
  netflow_internal_flows_only = null
  # netflow_observation_domain_id - (optional) is a type of number
  netflow_observation_domain_id = null
  # netflow_sampling_rate - (optional) is a type of number
  netflow_sampling_rate = null
  # network_resource_control_enabled - (optional) is a type of bool
  network_resource_control_enabled = null
  # network_resource_control_version - (optional) is a type of string
  network_resource_control_version = null
  # nfs_maximum_mbit - (optional) is a type of number
  nfs_maximum_mbit = null
  # nfs_reservation_mbit - (optional) is a type of number
  nfs_reservation_mbit = null
  # nfs_share_count - (optional) is a type of number
  nfs_share_count = null
  # nfs_share_level - (optional) is a type of string
  nfs_share_level = null
  # notify_switches - (optional) is a type of bool
  notify_switches = null
  # port_private_secondary_vlan_id - (optional) is a type of number
  port_private_secondary_vlan_id = null
  # standby_uplinks - (optional) is a type of list of string
  standby_uplinks = []
  # tags - (optional) is a type of set of string
  tags = []
  # teaming_policy - (optional) is a type of string
  teaming_policy = null
  # tx_uplink - (optional) is a type of bool
  tx_uplink = null
  # uplinks - (optional) is a type of list of string
  uplinks = []
  # vdp_maximum_mbit - (optional) is a type of number
  vdp_maximum_mbit = null
  # vdp_reservation_mbit - (optional) is a type of number
  vdp_reservation_mbit = null
  # vdp_share_count - (optional) is a type of number
  vdp_share_count = null
  # vdp_share_level - (optional) is a type of string
  vdp_share_level = null
  # version - (optional) is a type of string
  version = null
  # virtualmachine_maximum_mbit - (optional) is a type of number
  virtualmachine_maximum_mbit = null
  # virtualmachine_reservation_mbit - (optional) is a type of number
  virtualmachine_reservation_mbit = null
  # virtualmachine_share_count - (optional) is a type of number
  virtualmachine_share_count = null
  # virtualmachine_share_level - (optional) is a type of string
  virtualmachine_share_level = null
  # vlan_id - (optional) is a type of number
  vlan_id = null
  # vmotion_maximum_mbit - (optional) is a type of number
  vmotion_maximum_mbit = null
  # vmotion_reservation_mbit - (optional) is a type of number
  vmotion_reservation_mbit = null
  # vmotion_share_count - (optional) is a type of number
  vmotion_share_count = null
  # vmotion_share_level - (optional) is a type of string
  vmotion_share_level = null
  # vsan_maximum_mbit - (optional) is a type of number
  vsan_maximum_mbit = null
  # vsan_reservation_mbit - (optional) is a type of number
  vsan_reservation_mbit = null
  # vsan_share_count - (optional) is a type of number
  vsan_share_count = null
  # vsan_share_level - (optional) is a type of string
  vsan_share_level = null

  host = [{
    devices        = []
    host_system_id = null
  }]

  pvlan_mapping = [{
    primary_vlan_id   = null
    pvlan_type        = null
    secondary_vlan_id = null
  }]

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

variable "block_all_ports" {
  description = "(optional) - Indicates whether to block all ports by default."
  type        = bool
  default     = null
}

variable "check_beacon" {
  description = "(optional) - Enable beacon probing on the ports this policy applies to."
  type        = bool
  default     = null
}

variable "contact_detail" {
  description = "(optional) - The contact detail for this DVS."
  type        = string
  default     = null
}

variable "contact_name" {
  description = "(optional) - The contact name for this DVS."
  type        = string
  default     = null
}

variable "custom_attributes" {
  description = "(optional) - A list of custom attributes to set on this resource."
  type        = map(string)
  default     = null
}

variable "datacenter_id" {
  description = "(required) - The ID of the datacenter to create this virtual switch in."
  type        = string
}

variable "description" {
  description = "(optional) - The description of the DVS."
  type        = string
  default     = null
}

variable "directpath_gen2_allowed" {
  description = "(optional) - Allow VMDirectPath Gen2 on the ports this policy applies to."
  type        = bool
  default     = null
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

variable "faulttolerance_maximum_mbit" {
  description = "(optional) - The maximum allowed usage for the faultTolerance traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "faulttolerance_reservation_mbit" {
  description = "(optional) - The amount of guaranteed bandwidth for the faultTolerance traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "faulttolerance_share_count" {
  description = "(optional) - The amount of shares to allocate to the faultTolerance traffic class for a custom share level."
  type        = number
  default     = null
}

variable "faulttolerance_share_level" {
  description = "(optional) - The allocation level for the faultTolerance traffic class. Can be one of high, low, normal, or custom."
  type        = string
  default     = null
}

variable "folder" {
  description = "(optional) - The folder to create this virtual switch in, relative to the datacenter."
  type        = string
  default     = null
}

variable "hbr_maximum_mbit" {
  description = "(optional) - The maximum allowed usage for the hbr traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "hbr_reservation_mbit" {
  description = "(optional) - The amount of guaranteed bandwidth for the hbr traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "hbr_share_count" {
  description = "(optional) - The amount of shares to allocate to the hbr traffic class for a custom share level."
  type        = number
  default     = null
}

variable "hbr_share_level" {
  description = "(optional) - The allocation level for the hbr traffic class. Can be one of high, low, normal, or custom."
  type        = string
  default     = null
}

variable "ignore_other_pvlan_mappings" {
  description = "(optional) - Whether to ignore existing PVLAN mappings not managed by this resource. Defaults to false."
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

variable "ipv4_address" {
  description = "(optional) - The IPv4 address of the switch. This can be used to see the DVS as a unique device with NetFlow."
  type        = string
  default     = null
}

variable "iscsi_maximum_mbit" {
  description = "(optional) - The maximum allowed usage for the iSCSI traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "iscsi_reservation_mbit" {
  description = "(optional) - The amount of guaranteed bandwidth for the iSCSI traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "iscsi_share_count" {
  description = "(optional) - The amount of shares to allocate to the iSCSI traffic class for a custom share level."
  type        = number
  default     = null
}

variable "iscsi_share_level" {
  description = "(optional) - The allocation level for the iSCSI traffic class. Can be one of high, low, normal, or custom."
  type        = string
  default     = null
}

variable "lacp_api_version" {
  description = "(optional) - The Link Aggregation Control Protocol group version in the switch. Can be one of singleLag or multipleLag."
  type        = string
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

variable "link_discovery_operation" {
  description = "(optional) - Whether to advertise or listen for link discovery. Valid values are advertise, both, listen, and none."
  type        = string
  default     = null
}

variable "link_discovery_protocol" {
  description = "(optional) - The discovery protocol type. Valid values are cdp and lldp."
  type        = string
  default     = null
}

variable "management_maximum_mbit" {
  description = "(optional) - The maximum allowed usage for the management traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "management_reservation_mbit" {
  description = "(optional) - The amount of guaranteed bandwidth for the management traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "management_share_count" {
  description = "(optional) - The amount of shares to allocate to the management traffic class for a custom share level."
  type        = number
  default     = null
}

variable "management_share_level" {
  description = "(optional) - The allocation level for the management traffic class. Can be one of high, low, normal, or custom."
  type        = string
  default     = null
}

variable "max_mtu" {
  description = "(optional) - The maximum MTU on the switch."
  type        = number
  default     = null
}

variable "multicast_filtering_mode" {
  description = "(optional) - The multicast filtering mode on the switch. Can be one of legacyFiltering, or snooping."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name for the DVS. Must be unique in the folder that it is being created in."
  type        = string
}

variable "netflow_active_flow_timeout" {
  description = "(optional) - The number of seconds after which active flows are forced to be exported to the collector."
  type        = number
  default     = null
}

variable "netflow_collector_ip_address" {
  description = "(optional) - IP address for the netflow collector, using IPv4 or IPv6. IPv6 is supported in vSphere Distributed Switch Version 6.0 or later."
  type        = string
  default     = null
}

variable "netflow_collector_port" {
  description = "(optional) - The port for the netflow collector."
  type        = number
  default     = null
}

variable "netflow_enabled" {
  description = "(optional) - Indicates whether to enable netflow on all ports."
  type        = bool
  default     = null
}

variable "netflow_idle_flow_timeout" {
  description = "(optional) - The number of seconds after which idle flows are forced to be exported to the collector."
  type        = number
  default     = null
}

variable "netflow_internal_flows_only" {
  description = "(optional) - Whether to limit analysis to traffic that has both source and destination served by the same host."
  type        = bool
  default     = null
}

variable "netflow_observation_domain_id" {
  description = "(optional) - The observation Domain ID for the netflow collector."
  type        = number
  default     = null
}

variable "netflow_sampling_rate" {
  description = "(optional) - The ratio of total number of packets to the number of packets analyzed. Set to 0 to disable sampling, meaning that all packets are analyzed."
  type        = number
  default     = null
}

variable "network_resource_control_enabled" {
  description = "(optional) - Whether or not to enable network resource control, enabling advanced traffic shaping and resource control features."
  type        = bool
  default     = null
}

variable "network_resource_control_version" {
  description = "(optional) - The network I/O control version to use. Can be one of version2 or version3."
  type        = string
  default     = null
}

variable "nfs_maximum_mbit" {
  description = "(optional) - The maximum allowed usage for the nfs traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "nfs_reservation_mbit" {
  description = "(optional) - The amount of guaranteed bandwidth for the nfs traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "nfs_share_count" {
  description = "(optional) - The amount of shares to allocate to the nfs traffic class for a custom share level."
  type        = number
  default     = null
}

variable "nfs_share_level" {
  description = "(optional) - The allocation level for the nfs traffic class. Can be one of high, low, normal, or custom."
  type        = string
  default     = null
}

variable "notify_switches" {
  description = "(optional) - If true, the teaming policy will notify the broadcast network of a NIC failover, triggering cache updates."
  type        = bool
  default     = null
}

variable "port_private_secondary_vlan_id" {
  description = "(optional) - The secondary VLAN ID for this port."
  type        = number
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

variable "tx_uplink" {
  description = "(optional) - If true, a copy of packets sent to the switch will always be forwarded to an uplink in addition to the regular packet forwarded done by the switch."
  type        = bool
  default     = null
}

variable "uplinks" {
  description = "(optional) - A list of uplink ports. The contents of this list control both the uplink count and names of the uplinks on the DVS across hosts."
  type        = list(string)
  default     = null
}

variable "vdp_maximum_mbit" {
  description = "(optional) - The maximum allowed usage for the vdp traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "vdp_reservation_mbit" {
  description = "(optional) - The amount of guaranteed bandwidth for the vdp traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "vdp_share_count" {
  description = "(optional) - The amount of shares to allocate to the vdp traffic class for a custom share level."
  type        = number
  default     = null
}

variable "vdp_share_level" {
  description = "(optional) - The allocation level for the vdp traffic class. Can be one of high, low, normal, or custom."
  type        = string
  default     = null
}

variable "version" {
  description = "(optional) - The version of this virtual switch. Allowed versions are 6.5.0, 6.0.0, 5.5.0, 5.1.0, and 5.0.0."
  type        = string
  default     = null
}

variable "virtualmachine_maximum_mbit" {
  description = "(optional) - The maximum allowed usage for the virtualMachine traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "virtualmachine_reservation_mbit" {
  description = "(optional) - The amount of guaranteed bandwidth for the virtualMachine traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "virtualmachine_share_count" {
  description = "(optional) - The amount of shares to allocate to the virtualMachine traffic class for a custom share level."
  type        = number
  default     = null
}

variable "virtualmachine_share_level" {
  description = "(optional) - The allocation level for the virtualMachine traffic class. Can be one of high, low, normal, or custom."
  type        = string
  default     = null
}

variable "vlan_id" {
  description = "(optional) - The VLAN ID for single VLAN mode. 0 denotes no VLAN."
  type        = number
  default     = null
}

variable "vmotion_maximum_mbit" {
  description = "(optional) - The maximum allowed usage for the vmotion traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "vmotion_reservation_mbit" {
  description = "(optional) - The amount of guaranteed bandwidth for the vmotion traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "vmotion_share_count" {
  description = "(optional) - The amount of shares to allocate to the vmotion traffic class for a custom share level."
  type        = number
  default     = null
}

variable "vmotion_share_level" {
  description = "(optional) - The allocation level for the vmotion traffic class. Can be one of high, low, normal, or custom."
  type        = string
  default     = null
}

variable "vsan_maximum_mbit" {
  description = "(optional) - The maximum allowed usage for the vsan traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "vsan_reservation_mbit" {
  description = "(optional) - The amount of guaranteed bandwidth for the vsan traffic class, in Mbits/sec."
  type        = number
  default     = null
}

variable "vsan_share_count" {
  description = "(optional) - The amount of shares to allocate to the vsan traffic class for a custom share level."
  type        = number
  default     = null
}

variable "vsan_share_level" {
  description = "(optional) - The allocation level for the vsan traffic class. Can be one of high, low, normal, or custom."
  type        = string
  default     = null
}

variable "host" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      devices        = list(string)
      host_system_id = string
    }
  ))
  default = []
}

variable "pvlan_mapping" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      primary_vlan_id   = number
      pvlan_type        = string
      secondary_vlan_id = number
    }
  ))
  default = []
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
resource "vsphere_distributed_virtual_switch" "this" {
  active_uplinks                    = var.active_uplinks
  allow_forged_transmits            = var.allow_forged_transmits
  allow_mac_changes                 = var.allow_mac_changes
  allow_promiscuous                 = var.allow_promiscuous
  block_all_ports                   = var.block_all_ports
  check_beacon                      = var.check_beacon
  contact_detail                    = var.contact_detail
  contact_name                      = var.contact_name
  custom_attributes                 = var.custom_attributes
  datacenter_id                     = var.datacenter_id
  description                       = var.description
  directpath_gen2_allowed           = var.directpath_gen2_allowed
  egress_shaping_average_bandwidth  = var.egress_shaping_average_bandwidth
  egress_shaping_burst_size         = var.egress_shaping_burst_size
  egress_shaping_enabled            = var.egress_shaping_enabled
  egress_shaping_peak_bandwidth     = var.egress_shaping_peak_bandwidth
  failback                          = var.failback
  faulttolerance_maximum_mbit       = var.faulttolerance_maximum_mbit
  faulttolerance_reservation_mbit   = var.faulttolerance_reservation_mbit
  faulttolerance_share_count        = var.faulttolerance_share_count
  faulttolerance_share_level        = var.faulttolerance_share_level
  folder                            = var.folder
  hbr_maximum_mbit                  = var.hbr_maximum_mbit
  hbr_reservation_mbit              = var.hbr_reservation_mbit
  hbr_share_count                   = var.hbr_share_count
  hbr_share_level                   = var.hbr_share_level
  ignore_other_pvlan_mappings       = var.ignore_other_pvlan_mappings
  ingress_shaping_average_bandwidth = var.ingress_shaping_average_bandwidth
  ingress_shaping_burst_size        = var.ingress_shaping_burst_size
  ingress_shaping_enabled           = var.ingress_shaping_enabled
  ingress_shaping_peak_bandwidth    = var.ingress_shaping_peak_bandwidth
  ipv4_address                      = var.ipv4_address
  iscsi_maximum_mbit                = var.iscsi_maximum_mbit
  iscsi_reservation_mbit            = var.iscsi_reservation_mbit
  iscsi_share_count                 = var.iscsi_share_count
  iscsi_share_level                 = var.iscsi_share_level
  lacp_api_version                  = var.lacp_api_version
  lacp_enabled                      = var.lacp_enabled
  lacp_mode                         = var.lacp_mode
  link_discovery_operation          = var.link_discovery_operation
  link_discovery_protocol           = var.link_discovery_protocol
  management_maximum_mbit           = var.management_maximum_mbit
  management_reservation_mbit       = var.management_reservation_mbit
  management_share_count            = var.management_share_count
  management_share_level            = var.management_share_level
  max_mtu                           = var.max_mtu
  multicast_filtering_mode          = var.multicast_filtering_mode
  name                              = var.name
  netflow_active_flow_timeout       = var.netflow_active_flow_timeout
  netflow_collector_ip_address      = var.netflow_collector_ip_address
  netflow_collector_port            = var.netflow_collector_port
  netflow_enabled                   = var.netflow_enabled
  netflow_idle_flow_timeout         = var.netflow_idle_flow_timeout
  netflow_internal_flows_only       = var.netflow_internal_flows_only
  netflow_observation_domain_id     = var.netflow_observation_domain_id
  netflow_sampling_rate             = var.netflow_sampling_rate
  network_resource_control_enabled  = var.network_resource_control_enabled
  network_resource_control_version  = var.network_resource_control_version
  nfs_maximum_mbit                  = var.nfs_maximum_mbit
  nfs_reservation_mbit              = var.nfs_reservation_mbit
  nfs_share_count                   = var.nfs_share_count
  nfs_share_level                   = var.nfs_share_level
  notify_switches                   = var.notify_switches
  port_private_secondary_vlan_id    = var.port_private_secondary_vlan_id
  standby_uplinks                   = var.standby_uplinks
  tags                              = var.tags
  teaming_policy                    = var.teaming_policy
  tx_uplink                         = var.tx_uplink
  uplinks                           = var.uplinks
  vdp_maximum_mbit                  = var.vdp_maximum_mbit
  vdp_reservation_mbit              = var.vdp_reservation_mbit
  vdp_share_count                   = var.vdp_share_count
  vdp_share_level                   = var.vdp_share_level
  version                           = var.version
  virtualmachine_maximum_mbit       = var.virtualmachine_maximum_mbit
  virtualmachine_reservation_mbit   = var.virtualmachine_reservation_mbit
  virtualmachine_share_count        = var.virtualmachine_share_count
  virtualmachine_share_level        = var.virtualmachine_share_level
  vlan_id                           = var.vlan_id
  vmotion_maximum_mbit              = var.vmotion_maximum_mbit
  vmotion_reservation_mbit          = var.vmotion_reservation_mbit
  vmotion_share_count               = var.vmotion_share_count
  vmotion_share_level               = var.vmotion_share_level
  vsan_maximum_mbit                 = var.vsan_maximum_mbit
  vsan_reservation_mbit             = var.vsan_reservation_mbit
  vsan_share_count                  = var.vsan_share_count
  vsan_share_level                  = var.vsan_share_level

  dynamic "host" {
    for_each = var.host
    content {
      devices        = host.value["devices"]
      host_system_id = host.value["host_system_id"]
    }
  }

  dynamic "pvlan_mapping" {
    for_each = var.pvlan_mapping
    content {
      primary_vlan_id   = pvlan_mapping.value["primary_vlan_id"]
      pvlan_type        = pvlan_mapping.value["pvlan_type"]
      secondary_vlan_id = pvlan_mapping.value["secondary_vlan_id"]
    }
  }

  dynamic "vlan_range" {
    for_each = var.vlan_range
    content {
      max_vlan = vlan_range.value["max_vlan"]
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
  value       = vsphere_distributed_virtual_switch.this.active_uplinks
}

output "allow_forged_transmits" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.allow_forged_transmits
}

output "allow_mac_changes" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.allow_mac_changes
}

output "allow_promiscuous" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.allow_promiscuous
}

output "block_all_ports" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.block_all_ports
}

output "check_beacon" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.check_beacon
}

output "config_version" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.config_version
}

output "directpath_gen2_allowed" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.directpath_gen2_allowed
}

output "egress_shaping_average_bandwidth" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.egress_shaping_average_bandwidth
}

output "egress_shaping_burst_size" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.egress_shaping_burst_size
}

output "egress_shaping_enabled" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.egress_shaping_enabled
}

output "egress_shaping_peak_bandwidth" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.egress_shaping_peak_bandwidth
}

output "failback" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.failback
}

output "faulttolerance_maximum_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.faulttolerance_maximum_mbit
}

output "faulttolerance_reservation_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.faulttolerance_reservation_mbit
}

output "faulttolerance_share_count" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.faulttolerance_share_count
}

output "faulttolerance_share_level" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.faulttolerance_share_level
}

output "hbr_maximum_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.hbr_maximum_mbit
}

output "hbr_reservation_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.hbr_reservation_mbit
}

output "hbr_share_count" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.hbr_share_count
}

output "hbr_share_level" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.hbr_share_level
}

output "id" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.id
}

output "ingress_shaping_average_bandwidth" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.ingress_shaping_average_bandwidth
}

output "ingress_shaping_burst_size" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.ingress_shaping_burst_size
}

output "ingress_shaping_enabled" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.ingress_shaping_enabled
}

output "ingress_shaping_peak_bandwidth" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.ingress_shaping_peak_bandwidth
}

output "iscsi_maximum_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.iscsi_maximum_mbit
}

output "iscsi_reservation_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.iscsi_reservation_mbit
}

output "iscsi_share_count" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.iscsi_share_count
}

output "iscsi_share_level" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.iscsi_share_level
}

output "lacp_api_version" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.lacp_api_version
}

output "lacp_enabled" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.lacp_enabled
}

output "lacp_mode" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.lacp_mode
}

output "management_maximum_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.management_maximum_mbit
}

output "management_reservation_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.management_reservation_mbit
}

output "management_share_count" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.management_share_count
}

output "management_share_level" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.management_share_level
}

output "max_mtu" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.max_mtu
}

output "multicast_filtering_mode" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.multicast_filtering_mode
}

output "netflow_enabled" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.netflow_enabled
}

output "network_resource_control_version" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.network_resource_control_version
}

output "nfs_maximum_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.nfs_maximum_mbit
}

output "nfs_reservation_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.nfs_reservation_mbit
}

output "nfs_share_count" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.nfs_share_count
}

output "nfs_share_level" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.nfs_share_level
}

output "notify_switches" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.notify_switches
}

output "port_private_secondary_vlan_id" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.port_private_secondary_vlan_id
}

output "standby_uplinks" {
  description = "returns a list of string"
  value       = vsphere_distributed_virtual_switch.this.standby_uplinks
}

output "teaming_policy" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.teaming_policy
}

output "tx_uplink" {
  description = "returns a bool"
  value       = vsphere_distributed_virtual_switch.this.tx_uplink
}

output "uplinks" {
  description = "returns a list of string"
  value       = vsphere_distributed_virtual_switch.this.uplinks
}

output "vdp_maximum_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.vdp_maximum_mbit
}

output "vdp_reservation_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.vdp_reservation_mbit
}

output "vdp_share_count" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.vdp_share_count
}

output "vdp_share_level" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.vdp_share_level
}

output "version" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.version
}

output "virtualmachine_maximum_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.virtualmachine_maximum_mbit
}

output "virtualmachine_reservation_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.virtualmachine_reservation_mbit
}

output "virtualmachine_share_count" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.virtualmachine_share_count
}

output "virtualmachine_share_level" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.virtualmachine_share_level
}

output "vlan_id" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.vlan_id
}

output "vmotion_maximum_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.vmotion_maximum_mbit
}

output "vmotion_reservation_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.vmotion_reservation_mbit
}

output "vmotion_share_count" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.vmotion_share_count
}

output "vmotion_share_level" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.vmotion_share_level
}

output "vsan_maximum_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.vsan_maximum_mbit
}

output "vsan_reservation_mbit" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.vsan_reservation_mbit
}

output "vsan_share_count" {
  description = "returns a number"
  value       = vsphere_distributed_virtual_switch.this.vsan_share_count
}

output "vsan_share_level" {
  description = "returns a string"
  value       = vsphere_distributed_virtual_switch.this.vsan_share_level
}

output "this" {
  value = vsphere_distributed_virtual_switch.this
}
```

[top](#index)