# fortios_system_ha

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
module "fortios_system_ha" {
  source = "./modules/fortios/r/fortios_system_ha"

  # arps - (optional) is a type of number
  arps = null
  # arps_interval - (optional) is a type of number
  arps_interval = null
  # authentication - (optional) is a type of string
  authentication = null
  # cpu_threshold - (optional) is a type of string
  cpu_threshold = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # encryption - (optional) is a type of string
  encryption = null
  # ftp_proxy_threshold - (optional) is a type of string
  ftp_proxy_threshold = null
  # gratuitous_arps - (optional) is a type of string
  gratuitous_arps = null
  # group_id - (optional) is a type of number
  group_id = null
  # group_name - (optional) is a type of string
  group_name = null
  # ha_direct - (optional) is a type of string
  ha_direct = null
  # ha_eth_type - (optional) is a type of string
  ha_eth_type = null
  # ha_mgmt_status - (optional) is a type of string
  ha_mgmt_status = null
  # ha_uptime_diff_margin - (optional) is a type of number
  ha_uptime_diff_margin = null
  # hb_interval - (optional) is a type of number
  hb_interval = null
  # hb_lost_threshold - (optional) is a type of number
  hb_lost_threshold = null
  # hbdev - (optional) is a type of string
  hbdev = null
  # hc_eth_type - (optional) is a type of string
  hc_eth_type = null
  # hello_holddown - (optional) is a type of number
  hello_holddown = null
  # http_proxy_threshold - (optional) is a type of string
  http_proxy_threshold = null
  # imap_proxy_threshold - (optional) is a type of string
  imap_proxy_threshold = null
  # inter_cluster_session_sync - (optional) is a type of string
  inter_cluster_session_sync = null
  # key - (optional) is a type of string
  key = null
  # l2ep_eth_type - (optional) is a type of string
  l2ep_eth_type = null
  # link_failed_signal - (optional) is a type of string
  link_failed_signal = null
  # load_balance_all - (optional) is a type of string
  load_balance_all = null
  # logical_sn - (optional) is a type of string
  logical_sn = null
  # memory_compatible_mode - (optional) is a type of string
  memory_compatible_mode = null
  # memory_threshold - (optional) is a type of string
  memory_threshold = null
  # mode - (optional) is a type of string
  mode = null
  # monitor - (optional) is a type of string
  monitor = null
  # multicast_ttl - (optional) is a type of number
  multicast_ttl = null
  # nntp_proxy_threshold - (optional) is a type of string
  nntp_proxy_threshold = null
  # override - (optional) is a type of string
  override = null
  # override_wait_time - (optional) is a type of number
  override_wait_time = null
  # password - (optional) is a type of string
  password = null
  # pingserver_failover_threshold - (optional) is a type of number
  pingserver_failover_threshold = null
  # pingserver_flip_timeout - (optional) is a type of number
  pingserver_flip_timeout = null
  # pingserver_monitor_interface - (optional) is a type of string
  pingserver_monitor_interface = null
  # pingserver_secondary_force_reset - (optional) is a type of string
  pingserver_secondary_force_reset = null
  # pingserver_slave_force_reset - (optional) is a type of string
  pingserver_slave_force_reset = null
  # pop3_proxy_threshold - (optional) is a type of string
  pop3_proxy_threshold = null
  # priority - (optional) is a type of number
  priority = null
  # route_hold - (optional) is a type of number
  route_hold = null
  # route_ttl - (optional) is a type of number
  route_ttl = null
  # route_wait - (optional) is a type of number
  route_wait = null
  # schedule - (optional) is a type of string
  schedule = null
  # session_pickup - (optional) is a type of string
  session_pickup = null
  # session_pickup_connectionless - (optional) is a type of string
  session_pickup_connectionless = null
  # session_pickup_delay - (optional) is a type of string
  session_pickup_delay = null
  # session_pickup_expectation - (optional) is a type of string
  session_pickup_expectation = null
  # session_pickup_nat - (optional) is a type of string
  session_pickup_nat = null
  # session_sync_dev - (optional) is a type of string
  session_sync_dev = null
  # smtp_proxy_threshold - (optional) is a type of string
  smtp_proxy_threshold = null
  # ssd_failover - (optional) is a type of string
  ssd_failover = null
  # standalone_config_sync - (optional) is a type of string
  standalone_config_sync = null
  # standalone_mgmt_vdom - (optional) is a type of string
  standalone_mgmt_vdom = null
  # sync_config - (optional) is a type of string
  sync_config = null
  # sync_packet_balance - (optional) is a type of string
  sync_packet_balance = null
  # unicast_hb - (optional) is a type of string
  unicast_hb = null
  # unicast_hb_netmask - (optional) is a type of string
  unicast_hb_netmask = null
  # unicast_hb_peerip - (optional) is a type of string
  unicast_hb_peerip = null
  # uninterruptible_upgrade - (optional) is a type of string
  uninterruptible_upgrade = null
  # vcluster2 - (optional) is a type of string
  vcluster2 = null
  # vcluster_id - (optional) is a type of number
  vcluster_id = null
  # vdom - (optional) is a type of string
  vdom = null
  # weight - (optional) is a type of string
  weight = null

  ha_mgmt_interfaces = [{
    dst       = null
    gateway   = null
    gateway6  = null
    id        = null
    interface = null
  }]

  secondary_vcluster = [{
    monitor                          = null
    override                         = null
    override_wait_time               = null
    pingserver_failover_threshold    = null
    pingserver_monitor_interface     = null
    pingserver_secondary_force_reset = null
    pingserver_slave_force_reset     = null
    priority                         = null
    vcluster_id                      = null
    vdom                             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "arps" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "arps_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "authentication" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cpu_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "encryption" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ftp_proxy_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gratuitous_arps" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha_direct" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha_eth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha_mgmt_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha_uptime_diff_margin" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hb_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hb_lost_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hbdev" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hc_eth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hello_holddown" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "http_proxy_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "imap_proxy_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "inter_cluster_session_sync" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "l2ep_eth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "link_failed_signal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "load_balance_all" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "logical_sn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "memory_compatible_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "memory_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multicast_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "nntp_proxy_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "override_wait_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pingserver_failover_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pingserver_flip_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "pingserver_monitor_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pingserver_secondary_force_reset" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pingserver_slave_force_reset" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pop3_proxy_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "route_hold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "route_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "route_wait" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_pickup" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_pickup_connectionless" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_pickup_delay" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_pickup_expectation" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_pickup_nat" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "session_sync_dev" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "smtp_proxy_threshold" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssd_failover" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "standalone_config_sync" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "standalone_mgmt_vdom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sync_config" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sync_packet_balance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unicast_hb" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unicast_hb_netmask" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "unicast_hb_peerip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uninterruptible_upgrade" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcluster2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcluster_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vdom" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "weight" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha_mgmt_interfaces" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dst       = string
      gateway   = string
      gateway6  = string
      id        = number
      interface = string
    }
  ))
  default = []
}

variable "secondary_vcluster" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      monitor                          = string
      override                         = string
      override_wait_time               = number
      pingserver_failover_threshold    = number
      pingserver_monitor_interface     = string
      pingserver_secondary_force_reset = string
      pingserver_slave_force_reset     = string
      priority                         = number
      vcluster_id                      = number
      vdom                             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_ha" "this" {
  arps                             = var.arps
  arps_interval                    = var.arps_interval
  authentication                   = var.authentication
  cpu_threshold                    = var.cpu_threshold
  dynamic_sort_subtable            = var.dynamic_sort_subtable
  encryption                       = var.encryption
  ftp_proxy_threshold              = var.ftp_proxy_threshold
  gratuitous_arps                  = var.gratuitous_arps
  group_id                         = var.group_id
  group_name                       = var.group_name
  ha_direct                        = var.ha_direct
  ha_eth_type                      = var.ha_eth_type
  ha_mgmt_status                   = var.ha_mgmt_status
  ha_uptime_diff_margin            = var.ha_uptime_diff_margin
  hb_interval                      = var.hb_interval
  hb_lost_threshold                = var.hb_lost_threshold
  hbdev                            = var.hbdev
  hc_eth_type                      = var.hc_eth_type
  hello_holddown                   = var.hello_holddown
  http_proxy_threshold             = var.http_proxy_threshold
  imap_proxy_threshold             = var.imap_proxy_threshold
  inter_cluster_session_sync       = var.inter_cluster_session_sync
  key                              = var.key
  l2ep_eth_type                    = var.l2ep_eth_type
  link_failed_signal               = var.link_failed_signal
  load_balance_all                 = var.load_balance_all
  logical_sn                       = var.logical_sn
  memory_compatible_mode           = var.memory_compatible_mode
  memory_threshold                 = var.memory_threshold
  mode                             = var.mode
  monitor                          = var.monitor
  multicast_ttl                    = var.multicast_ttl
  nntp_proxy_threshold             = var.nntp_proxy_threshold
  override                         = var.override
  override_wait_time               = var.override_wait_time
  password                         = var.password
  pingserver_failover_threshold    = var.pingserver_failover_threshold
  pingserver_flip_timeout          = var.pingserver_flip_timeout
  pingserver_monitor_interface     = var.pingserver_monitor_interface
  pingserver_secondary_force_reset = var.pingserver_secondary_force_reset
  pingserver_slave_force_reset     = var.pingserver_slave_force_reset
  pop3_proxy_threshold             = var.pop3_proxy_threshold
  priority                         = var.priority
  route_hold                       = var.route_hold
  route_ttl                        = var.route_ttl
  route_wait                       = var.route_wait
  schedule                         = var.schedule
  session_pickup                   = var.session_pickup
  session_pickup_connectionless    = var.session_pickup_connectionless
  session_pickup_delay             = var.session_pickup_delay
  session_pickup_expectation       = var.session_pickup_expectation
  session_pickup_nat               = var.session_pickup_nat
  session_sync_dev                 = var.session_sync_dev
  smtp_proxy_threshold             = var.smtp_proxy_threshold
  ssd_failover                     = var.ssd_failover
  standalone_config_sync           = var.standalone_config_sync
  standalone_mgmt_vdom             = var.standalone_mgmt_vdom
  sync_config                      = var.sync_config
  sync_packet_balance              = var.sync_packet_balance
  unicast_hb                       = var.unicast_hb
  unicast_hb_netmask               = var.unicast_hb_netmask
  unicast_hb_peerip                = var.unicast_hb_peerip
  uninterruptible_upgrade          = var.uninterruptible_upgrade
  vcluster2                        = var.vcluster2
  vcluster_id                      = var.vcluster_id
  vdom                             = var.vdom
  weight                           = var.weight

  dynamic "ha_mgmt_interfaces" {
    for_each = var.ha_mgmt_interfaces
    content {
      dst       = ha_mgmt_interfaces.value["dst"]
      gateway   = ha_mgmt_interfaces.value["gateway"]
      gateway6  = ha_mgmt_interfaces.value["gateway6"]
      id        = ha_mgmt_interfaces.value["id"]
      interface = ha_mgmt_interfaces.value["interface"]
    }
  }

  dynamic "secondary_vcluster" {
    for_each = var.secondary_vcluster
    content {
      monitor                          = secondary_vcluster.value["monitor"]
      override                         = secondary_vcluster.value["override"]
      override_wait_time               = secondary_vcluster.value["override_wait_time"]
      pingserver_failover_threshold    = secondary_vcluster.value["pingserver_failover_threshold"]
      pingserver_monitor_interface     = secondary_vcluster.value["pingserver_monitor_interface"]
      pingserver_secondary_force_reset = secondary_vcluster.value["pingserver_secondary_force_reset"]
      pingserver_slave_force_reset     = secondary_vcluster.value["pingserver_slave_force_reset"]
      priority                         = secondary_vcluster.value["priority"]
      vcluster_id                      = secondary_vcluster.value["vcluster_id"]
      vdom                             = secondary_vcluster.value["vdom"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arps" {
  description = "returns a number"
  value       = fortios_system_ha.this.arps
}

output "arps_interval" {
  description = "returns a number"
  value       = fortios_system_ha.this.arps_interval
}

output "authentication" {
  description = "returns a string"
  value       = fortios_system_ha.this.authentication
}

output "cpu_threshold" {
  description = "returns a string"
  value       = fortios_system_ha.this.cpu_threshold
}

output "encryption" {
  description = "returns a string"
  value       = fortios_system_ha.this.encryption
}

output "ftp_proxy_threshold" {
  description = "returns a string"
  value       = fortios_system_ha.this.ftp_proxy_threshold
}

output "gratuitous_arps" {
  description = "returns a string"
  value       = fortios_system_ha.this.gratuitous_arps
}

output "group_id" {
  description = "returns a number"
  value       = fortios_system_ha.this.group_id
}

output "group_name" {
  description = "returns a string"
  value       = fortios_system_ha.this.group_name
}

output "ha_direct" {
  description = "returns a string"
  value       = fortios_system_ha.this.ha_direct
}

output "ha_eth_type" {
  description = "returns a string"
  value       = fortios_system_ha.this.ha_eth_type
}

output "ha_mgmt_status" {
  description = "returns a string"
  value       = fortios_system_ha.this.ha_mgmt_status
}

output "ha_uptime_diff_margin" {
  description = "returns a number"
  value       = fortios_system_ha.this.ha_uptime_diff_margin
}

output "hb_interval" {
  description = "returns a number"
  value       = fortios_system_ha.this.hb_interval
}

output "hb_lost_threshold" {
  description = "returns a number"
  value       = fortios_system_ha.this.hb_lost_threshold
}

output "hbdev" {
  description = "returns a string"
  value       = fortios_system_ha.this.hbdev
}

output "hc_eth_type" {
  description = "returns a string"
  value       = fortios_system_ha.this.hc_eth_type
}

output "hello_holddown" {
  description = "returns a number"
  value       = fortios_system_ha.this.hello_holddown
}

output "http_proxy_threshold" {
  description = "returns a string"
  value       = fortios_system_ha.this.http_proxy_threshold
}

output "id" {
  description = "returns a string"
  value       = fortios_system_ha.this.id
}

output "imap_proxy_threshold" {
  description = "returns a string"
  value       = fortios_system_ha.this.imap_proxy_threshold
}

output "inter_cluster_session_sync" {
  description = "returns a string"
  value       = fortios_system_ha.this.inter_cluster_session_sync
}

output "l2ep_eth_type" {
  description = "returns a string"
  value       = fortios_system_ha.this.l2ep_eth_type
}

output "link_failed_signal" {
  description = "returns a string"
  value       = fortios_system_ha.this.link_failed_signal
}

output "load_balance_all" {
  description = "returns a string"
  value       = fortios_system_ha.this.load_balance_all
}

output "logical_sn" {
  description = "returns a string"
  value       = fortios_system_ha.this.logical_sn
}

output "memory_compatible_mode" {
  description = "returns a string"
  value       = fortios_system_ha.this.memory_compatible_mode
}

output "memory_threshold" {
  description = "returns a string"
  value       = fortios_system_ha.this.memory_threshold
}

output "mode" {
  description = "returns a string"
  value       = fortios_system_ha.this.mode
}

output "monitor" {
  description = "returns a string"
  value       = fortios_system_ha.this.monitor
}

output "multicast_ttl" {
  description = "returns a number"
  value       = fortios_system_ha.this.multicast_ttl
}

output "nntp_proxy_threshold" {
  description = "returns a string"
  value       = fortios_system_ha.this.nntp_proxy_threshold
}

output "override" {
  description = "returns a string"
  value       = fortios_system_ha.this.override
}

output "override_wait_time" {
  description = "returns a number"
  value       = fortios_system_ha.this.override_wait_time
}

output "pingserver_failover_threshold" {
  description = "returns a number"
  value       = fortios_system_ha.this.pingserver_failover_threshold
}

output "pingserver_flip_timeout" {
  description = "returns a number"
  value       = fortios_system_ha.this.pingserver_flip_timeout
}

output "pingserver_monitor_interface" {
  description = "returns a string"
  value       = fortios_system_ha.this.pingserver_monitor_interface
}

output "pingserver_secondary_force_reset" {
  description = "returns a string"
  value       = fortios_system_ha.this.pingserver_secondary_force_reset
}

output "pingserver_slave_force_reset" {
  description = "returns a string"
  value       = fortios_system_ha.this.pingserver_slave_force_reset
}

output "pop3_proxy_threshold" {
  description = "returns a string"
  value       = fortios_system_ha.this.pop3_proxy_threshold
}

output "priority" {
  description = "returns a number"
  value       = fortios_system_ha.this.priority
}

output "route_hold" {
  description = "returns a number"
  value       = fortios_system_ha.this.route_hold
}

output "route_ttl" {
  description = "returns a number"
  value       = fortios_system_ha.this.route_ttl
}

output "route_wait" {
  description = "returns a number"
  value       = fortios_system_ha.this.route_wait
}

output "schedule" {
  description = "returns a string"
  value       = fortios_system_ha.this.schedule
}

output "session_pickup" {
  description = "returns a string"
  value       = fortios_system_ha.this.session_pickup
}

output "session_pickup_connectionless" {
  description = "returns a string"
  value       = fortios_system_ha.this.session_pickup_connectionless
}

output "session_pickup_delay" {
  description = "returns a string"
  value       = fortios_system_ha.this.session_pickup_delay
}

output "session_pickup_expectation" {
  description = "returns a string"
  value       = fortios_system_ha.this.session_pickup_expectation
}

output "session_pickup_nat" {
  description = "returns a string"
  value       = fortios_system_ha.this.session_pickup_nat
}

output "session_sync_dev" {
  description = "returns a string"
  value       = fortios_system_ha.this.session_sync_dev
}

output "smtp_proxy_threshold" {
  description = "returns a string"
  value       = fortios_system_ha.this.smtp_proxy_threshold
}

output "ssd_failover" {
  description = "returns a string"
  value       = fortios_system_ha.this.ssd_failover
}

output "standalone_config_sync" {
  description = "returns a string"
  value       = fortios_system_ha.this.standalone_config_sync
}

output "standalone_mgmt_vdom" {
  description = "returns a string"
  value       = fortios_system_ha.this.standalone_mgmt_vdom
}

output "sync_config" {
  description = "returns a string"
  value       = fortios_system_ha.this.sync_config
}

output "sync_packet_balance" {
  description = "returns a string"
  value       = fortios_system_ha.this.sync_packet_balance
}

output "unicast_hb" {
  description = "returns a string"
  value       = fortios_system_ha.this.unicast_hb
}

output "unicast_hb_netmask" {
  description = "returns a string"
  value       = fortios_system_ha.this.unicast_hb_netmask
}

output "unicast_hb_peerip" {
  description = "returns a string"
  value       = fortios_system_ha.this.unicast_hb_peerip
}

output "uninterruptible_upgrade" {
  description = "returns a string"
  value       = fortios_system_ha.this.uninterruptible_upgrade
}

output "vcluster2" {
  description = "returns a string"
  value       = fortios_system_ha.this.vcluster2
}

output "vcluster_id" {
  description = "returns a number"
  value       = fortios_system_ha.this.vcluster_id
}

output "vdom" {
  description = "returns a string"
  value       = fortios_system_ha.this.vdom
}

output "weight" {
  description = "returns a string"
  value       = fortios_system_ha.this.weight
}

output "this" {
  value = fortios_system_ha.this
}
```

[top](#index)