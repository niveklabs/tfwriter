# fortios_system_ha

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/fortios/d/fortios_system_ha"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_ha" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "arps" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.arps
}

output "arps_interval" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.arps_interval
}

output "authentication" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.authentication
}

output "cpu_threshold" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.cpu_threshold
}

output "encryption" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.encryption
}

output "ftp_proxy_threshold" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.ftp_proxy_threshold
}

output "gratuitous_arps" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.gratuitous_arps
}

output "group_id" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.group_id
}

output "group_name" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.group_name
}

output "ha_direct" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.ha_direct
}

output "ha_eth_type" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.ha_eth_type
}

output "ha_mgmt_interfaces" {
  description = "returns a list of object"
  value       = data.fortios_system_ha.this.ha_mgmt_interfaces
}

output "ha_mgmt_status" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.ha_mgmt_status
}

output "ha_uptime_diff_margin" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.ha_uptime_diff_margin
}

output "hb_interval" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.hb_interval
}

output "hb_lost_threshold" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.hb_lost_threshold
}

output "hbdev" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.hbdev
}

output "hc_eth_type" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.hc_eth_type
}

output "hello_holddown" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.hello_holddown
}

output "http_proxy_threshold" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.http_proxy_threshold
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.id
}

output "imap_proxy_threshold" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.imap_proxy_threshold
}

output "inter_cluster_session_sync" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.inter_cluster_session_sync
}

output "key" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.key
  sensitive   = true
}

output "l2ep_eth_type" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.l2ep_eth_type
}

output "link_failed_signal" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.link_failed_signal
}

output "load_balance_all" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.load_balance_all
}

output "logical_sn" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.logical_sn
}

output "memory_compatible_mode" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.memory_compatible_mode
}

output "memory_threshold" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.memory_threshold
}

output "mode" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.mode
}

output "monitor" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.monitor
}

output "multicast_ttl" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.multicast_ttl
}

output "nntp_proxy_threshold" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.nntp_proxy_threshold
}

output "override" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.override
}

output "override_wait_time" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.override_wait_time
}

output "password" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.password
  sensitive   = true
}

output "pingserver_failover_threshold" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.pingserver_failover_threshold
}

output "pingserver_flip_timeout" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.pingserver_flip_timeout
}

output "pingserver_monitor_interface" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.pingserver_monitor_interface
}

output "pingserver_secondary_force_reset" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.pingserver_secondary_force_reset
}

output "pingserver_slave_force_reset" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.pingserver_slave_force_reset
}

output "pop3_proxy_threshold" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.pop3_proxy_threshold
}

output "priority" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.priority
}

output "route_hold" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.route_hold
}

output "route_ttl" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.route_ttl
}

output "route_wait" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.route_wait
}

output "schedule" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.schedule
}

output "secondary_vcluster" {
  description = "returns a list of object"
  value       = data.fortios_system_ha.this.secondary_vcluster
}

output "session_pickup" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.session_pickup
}

output "session_pickup_connectionless" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.session_pickup_connectionless
}

output "session_pickup_delay" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.session_pickup_delay
}

output "session_pickup_expectation" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.session_pickup_expectation
}

output "session_pickup_nat" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.session_pickup_nat
}

output "session_sync_dev" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.session_sync_dev
}

output "smtp_proxy_threshold" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.smtp_proxy_threshold
}

output "ssd_failover" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.ssd_failover
}

output "standalone_config_sync" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.standalone_config_sync
}

output "standalone_mgmt_vdom" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.standalone_mgmt_vdom
}

output "sync_config" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.sync_config
}

output "sync_packet_balance" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.sync_packet_balance
}

output "unicast_hb" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.unicast_hb
}

output "unicast_hb_netmask" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.unicast_hb_netmask
}

output "unicast_hb_peerip" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.unicast_hb_peerip
}

output "uninterruptible_upgrade" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.uninterruptible_upgrade
}

output "vcluster2" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.vcluster2
}

output "vcluster_id" {
  description = "returns a number"
  value       = data.fortios_system_ha.this.vcluster_id
}

output "vdom" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.vdom
}

output "weight" {
  description = "returns a string"
  value       = data.fortios_system_ha.this.weight
}

output "this" {
  value = fortios_system_ha.this
}
```

[top](#index)