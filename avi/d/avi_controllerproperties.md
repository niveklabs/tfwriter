# avi_controllerproperties

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "avi_controllerproperties" {
  source = "./modules/avi/d/avi_controllerproperties"

  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_controllerproperties" "this" {
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "allow_admin_network_updates" {
  description = "returns a bool"
  value       = data.avi_controllerproperties.this.allow_admin_network_updates
}

output "allow_ip_forwarding" {
  description = "returns a bool"
  value       = data.avi_controllerproperties.this.allow_ip_forwarding
}

output "allow_unauthenticated_apis" {
  description = "returns a bool"
  value       = data.avi_controllerproperties.this.allow_unauthenticated_apis
}

output "allow_unauthenticated_nodes" {
  description = "returns a bool"
  value       = data.avi_controllerproperties.this.allow_unauthenticated_nodes
}

output "api_idle_timeout" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.api_idle_timeout
}

output "api_perf_logging_threshold" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.api_perf_logging_threshold
}

output "appviewx_compat_mode" {
  description = "returns a bool"
  value       = data.avi_controllerproperties.this.appviewx_compat_mode
}

output "attach_ip_retry_interval" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.attach_ip_retry_interval
}

output "attach_ip_retry_limit" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.attach_ip_retry_limit
}

output "bm_use_ansible" {
  description = "returns a bool"
  value       = data.avi_controllerproperties.this.bm_use_ansible
}

output "cleanup_expired_authtoken_timeout_period" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.cleanup_expired_authtoken_timeout_period
}

output "cleanup_sessions_timeout_period" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.cleanup_sessions_timeout_period
}

output "cloud_reconcile" {
  description = "returns a bool"
  value       = data.avi_controllerproperties.this.cloud_reconcile
}

output "cluster_ip_gratuitous_arp_period" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.cluster_ip_gratuitous_arp_period
}

output "consistency_check_timeout_period" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.consistency_check_timeout_period
}

output "crashed_se_reboot" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.crashed_se_reboot
}

output "dead_se_detection_timer" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.dead_se_detection_timer
}

output "default_minimum_api_timeout" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.default_minimum_api_timeout
}

output "dns_refresh_period" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.dns_refresh_period
}

output "dummy" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.dummy
}

output "enable_api_sharding" {
  description = "returns a bool"
  value       = data.avi_controllerproperties.this.enable_api_sharding
}

output "enable_memory_balancer" {
  description = "returns a bool"
  value       = data.avi_controllerproperties.this.enable_memory_balancer
}

output "fatal_error_lease_time" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.fatal_error_lease_time
}

output "id" {
  description = "returns a string"
  value       = data.avi_controllerproperties.this.id
}

output "max_dead_se_in_grp" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.max_dead_se_in_grp
}

output "max_pcap_per_tenant" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.max_pcap_per_tenant
}

output "max_seq_attach_ip_failures" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.max_seq_attach_ip_failures
}

output "max_seq_vnic_failures" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.max_seq_vnic_failures
}

output "permission_scoped_shared_admin_networks" {
  description = "returns a bool"
  value       = data.avi_controllerproperties.this.permission_scoped_shared_admin_networks
}

output "persistence_key_rotate_period" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.persistence_key_rotate_period
}

output "portal_token" {
  description = "returns a string"
  value       = data.avi_controllerproperties.this.portal_token
}

output "process_locked_useraccounts_timeout_period" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.process_locked_useraccounts_timeout_period
}

output "process_pki_profile_timeout_period" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.process_pki_profile_timeout_period
}

output "query_host_fail" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.query_host_fail
}

output "safenet_hsm_version" {
  description = "returns a string"
  value       = data.avi_controllerproperties.this.safenet_hsm_version
}

output "se_create_timeout" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.se_create_timeout
}

output "se_failover_attempt_interval" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.se_failover_attempt_interval
}

output "se_from_marketplace" {
  description = "returns a string"
  value       = data.avi_controllerproperties.this.se_from_marketplace
}

output "se_offline_del" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.se_offline_del
}

output "se_vnic_cooldown" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.se_vnic_cooldown
}

output "secure_channel_cleanup_timeout" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.secure_channel_cleanup_timeout
}

output "secure_channel_controller_token_timeout" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.secure_channel_controller_token_timeout
}

output "secure_channel_se_token_timeout" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.secure_channel_se_token_timeout
}

output "seupgrade_copy_pool_size" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.seupgrade_copy_pool_size
}

output "seupgrade_fabric_pool_size" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.seupgrade_fabric_pool_size
}

output "seupgrade_segroup_min_dead_timeout" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.seupgrade_segroup_min_dead_timeout
}

output "shared_ssl_certificates" {
  description = "returns a bool"
  value       = data.avi_controllerproperties.this.shared_ssl_certificates
}

output "ssl_certificate_expiry_warning_days" {
  description = "returns a list of number"
  value       = data.avi_controllerproperties.this.ssl_certificate_expiry_warning_days
}

output "unresponsive_se_reboot" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.unresponsive_se_reboot
}

output "upgrade_dns_ttl" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.upgrade_dns_ttl
}

output "upgrade_lease_time" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.upgrade_lease_time
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_controllerproperties.this.uuid
}

output "vnic_op_fail_time" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.vnic_op_fail_time
}

output "vs_apic_scaleout_timeout" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.vs_apic_scaleout_timeout
}

output "vs_awaiting_se_timeout" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.vs_awaiting_se_timeout
}

output "vs_key_rotate_period" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.vs_key_rotate_period
}

output "vs_scaleout_ready_check_interval" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.vs_scaleout_ready_check_interval
}

output "vs_se_attach_ip_fail" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.vs_se_attach_ip_fail
}

output "vs_se_bootup_fail" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.vs_se_bootup_fail
}

output "vs_se_create_fail" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.vs_se_create_fail
}

output "vs_se_ping_fail" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.vs_se_ping_fail
}

output "vs_se_vnic_fail" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.vs_se_vnic_fail
}

output "vs_se_vnic_ip_fail" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.vs_se_vnic_ip_fail
}

output "warmstart_se_reconnect_wait_time" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.warmstart_se_reconnect_wait_time
}

output "warmstart_vs_resync_wait_time" {
  description = "returns a number"
  value       = data.avi_controllerproperties.this.warmstart_vs_resync_wait_time
}

output "this" {
  value = avi_controllerproperties.this
}
```

[top](#index)