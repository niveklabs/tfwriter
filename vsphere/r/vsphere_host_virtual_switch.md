# vsphere_host_virtual_switch

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
module "vsphere_host_virtual_switch" {
  source = "./modules/vsphere/r/vsphere_host_virtual_switch"

  # active_nics - (required) is a type of list of string
  active_nics = []
  # allow_forged_transmits - (optional) is a type of bool
  allow_forged_transmits = null
  # allow_mac_changes - (optional) is a type of bool
  allow_mac_changes = null
  # allow_promiscuous - (optional) is a type of bool
  allow_promiscuous = null
  # beacon_interval - (optional) is a type of number
  beacon_interval = null
  # check_beacon - (optional) is a type of bool
  check_beacon = null
  # failback - (optional) is a type of bool
  failback = null
  # host_system_id - (required) is a type of string
  host_system_id = null
  # link_discovery_operation - (optional) is a type of string
  link_discovery_operation = null
  # link_discovery_protocol - (optional) is a type of string
  link_discovery_protocol = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # network_adapters - (required) is a type of list of string
  network_adapters = []
  # notify_switches - (optional) is a type of bool
  notify_switches = null
  # number_of_ports - (optional) is a type of number
  number_of_ports = null
  # shaping_average_bandwidth - (optional) is a type of number
  shaping_average_bandwidth = null
  # shaping_burst_size - (optional) is a type of number
  shaping_burst_size = null
  # shaping_enabled - (optional) is a type of bool
  shaping_enabled = null
  # shaping_peak_bandwidth - (optional) is a type of number
  shaping_peak_bandwidth = null
  # standby_nics - (required) is a type of list of string
  standby_nics = []
  # teaming_policy - (optional) is a type of string
  teaming_policy = null
}
```

[top](#index)

### Variables

```terraform
variable "active_nics" {
  description = "(required) - List of active network adapters used for load balancing."
  type        = list(string)
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

variable "beacon_interval" {
  description = "(optional) - Determines how often, in seconds, a beacon should be sent to probe for the validity of a link."
  type        = number
  default     = null
}

variable "check_beacon" {
  description = "(optional) - Enable beacon probing. Requires that the vSwitch has been configured to use a beacon. If disabled, link status is used only."
  type        = bool
  default     = null
}

variable "failback" {
  description = "(optional) - If true, the teaming policy will re-activate failed interfaces higher in precedence when they come back up."
  type        = bool
  default     = null
}

variable "host_system_id" {
  description = "(required) - The managed object ID of the host to set the virtual switch up on."
  type        = string
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

variable "mtu" {
  description = "(optional) - The maximum transmission unit (MTU) of the virtual switch in bytes."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - The name of the virtual switch."
  type        = string
}

variable "network_adapters" {
  description = "(required) - The list of network adapters to bind to this virtual switch."
  type        = list(string)
}

variable "notify_switches" {
  description = "(optional) - If true, the teaming policy will notify the broadcast network of a NIC failover, triggering cache updates."
  type        = bool
  default     = null
}

variable "number_of_ports" {
  description = "(optional) - The number of ports that this virtual switch is configured to use."
  type        = number
  default     = null
}

variable "shaping_average_bandwidth" {
  description = "(optional) - The average bandwidth in bits per second if traffic shaping is enabled."
  type        = number
  default     = null
}

variable "shaping_burst_size" {
  description = "(optional) - The maximum burst size allowed in bytes if traffic shaping is enabled."
  type        = number
  default     = null
}

variable "shaping_enabled" {
  description = "(optional) - Enable traffic shaping on this virtual switch or port group."
  type        = bool
  default     = null
}

variable "shaping_peak_bandwidth" {
  description = "(optional) - The peak bandwidth during bursts in bits per second if traffic shaping is enabled."
  type        = number
  default     = null
}

variable "standby_nics" {
  description = "(required) - List of standby network adapters used for failover."
  type        = list(string)
}

variable "teaming_policy" {
  description = "(optional) - The network adapter teaming policy. Can be one of loadbalance_ip, loadbalance_srcmac, loadbalance_srcid, or failover_explicit."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vsphere_host_virtual_switch" "this" {
  # active_nics - (required) is a type of list of string
  active_nics = var.active_nics
  # allow_forged_transmits - (optional) is a type of bool
  allow_forged_transmits = var.allow_forged_transmits
  # allow_mac_changes - (optional) is a type of bool
  allow_mac_changes = var.allow_mac_changes
  # allow_promiscuous - (optional) is a type of bool
  allow_promiscuous = var.allow_promiscuous
  # beacon_interval - (optional) is a type of number
  beacon_interval = var.beacon_interval
  # check_beacon - (optional) is a type of bool
  check_beacon = var.check_beacon
  # failback - (optional) is a type of bool
  failback = var.failback
  # host_system_id - (required) is a type of string
  host_system_id = var.host_system_id
  # link_discovery_operation - (optional) is a type of string
  link_discovery_operation = var.link_discovery_operation
  # link_discovery_protocol - (optional) is a type of string
  link_discovery_protocol = var.link_discovery_protocol
  # mtu - (optional) is a type of number
  mtu = var.mtu
  # name - (required) is a type of string
  name = var.name
  # network_adapters - (required) is a type of list of string
  network_adapters = var.network_adapters
  # notify_switches - (optional) is a type of bool
  notify_switches = var.notify_switches
  # number_of_ports - (optional) is a type of number
  number_of_ports = var.number_of_ports
  # shaping_average_bandwidth - (optional) is a type of number
  shaping_average_bandwidth = var.shaping_average_bandwidth
  # shaping_burst_size - (optional) is a type of number
  shaping_burst_size = var.shaping_burst_size
  # shaping_enabled - (optional) is a type of bool
  shaping_enabled = var.shaping_enabled
  # shaping_peak_bandwidth - (optional) is a type of number
  shaping_peak_bandwidth = var.shaping_peak_bandwidth
  # standby_nics - (required) is a type of list of string
  standby_nics = var.standby_nics
  # teaming_policy - (optional) is a type of string
  teaming_policy = var.teaming_policy
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vsphere_host_virtual_switch.this.id
}

output "this" {
  value = vsphere_host_virtual_switch.this
}
```

[top](#index)