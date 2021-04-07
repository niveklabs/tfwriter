# avi_controllerproperties

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
module "avi_controllerproperties" {
  source = "./modules/avi/r/avi_controllerproperties"

  # allow_admin_network_updates - (optional) is a type of bool
  allow_admin_network_updates = null
  # allow_ip_forwarding - (optional) is a type of bool
  allow_ip_forwarding = null
  # allow_unauthenticated_apis - (optional) is a type of bool
  allow_unauthenticated_apis = null
  # allow_unauthenticated_nodes - (optional) is a type of bool
  allow_unauthenticated_nodes = null
  # api_idle_timeout - (optional) is a type of number
  api_idle_timeout = null
  # api_perf_logging_threshold - (optional) is a type of number
  api_perf_logging_threshold = null
  # appviewx_compat_mode - (optional) is a type of bool
  appviewx_compat_mode = null
  # attach_ip_retry_interval - (optional) is a type of number
  attach_ip_retry_interval = null
  # attach_ip_retry_limit - (optional) is a type of number
  attach_ip_retry_limit = null
  # bm_use_ansible - (optional) is a type of bool
  bm_use_ansible = null
  # cleanup_expired_authtoken_timeout_period - (optional) is a type of number
  cleanup_expired_authtoken_timeout_period = null
  # cleanup_sessions_timeout_period - (optional) is a type of number
  cleanup_sessions_timeout_period = null
  # cloud_reconcile - (optional) is a type of bool
  cloud_reconcile = null
  # cluster_ip_gratuitous_arp_period - (optional) is a type of number
  cluster_ip_gratuitous_arp_period = null
  # consistency_check_timeout_period - (optional) is a type of number
  consistency_check_timeout_period = null
  # crashed_se_reboot - (optional) is a type of number
  crashed_se_reboot = null
  # dead_se_detection_timer - (optional) is a type of number
  dead_se_detection_timer = null
  # default_minimum_api_timeout - (optional) is a type of number
  default_minimum_api_timeout = null
  # dns_refresh_period - (optional) is a type of number
  dns_refresh_period = null
  # dummy - (optional) is a type of number
  dummy = null
  # enable_api_sharding - (optional) is a type of bool
  enable_api_sharding = null
  # enable_memory_balancer - (optional) is a type of bool
  enable_memory_balancer = null
  # fatal_error_lease_time - (optional) is a type of number
  fatal_error_lease_time = null
  # max_dead_se_in_grp - (optional) is a type of number
  max_dead_se_in_grp = null
  # max_pcap_per_tenant - (optional) is a type of number
  max_pcap_per_tenant = null
  # max_seq_attach_ip_failures - (optional) is a type of number
  max_seq_attach_ip_failures = null
  # max_seq_vnic_failures - (optional) is a type of number
  max_seq_vnic_failures = null
  # permission_scoped_shared_admin_networks - (optional) is a type of bool
  permission_scoped_shared_admin_networks = null
  # persistence_key_rotate_period - (optional) is a type of number
  persistence_key_rotate_period = null
  # portal_token - (optional) is a type of string
  portal_token = null
  # process_locked_useraccounts_timeout_period - (optional) is a type of number
  process_locked_useraccounts_timeout_period = null
  # process_pki_profile_timeout_period - (optional) is a type of number
  process_pki_profile_timeout_period = null
  # query_host_fail - (optional) is a type of number
  query_host_fail = null
  # safenet_hsm_version - (optional) is a type of string
  safenet_hsm_version = null
  # se_create_timeout - (optional) is a type of number
  se_create_timeout = null
  # se_failover_attempt_interval - (optional) is a type of number
  se_failover_attempt_interval = null
  # se_from_marketplace - (optional) is a type of string
  se_from_marketplace = null
  # se_offline_del - (optional) is a type of number
  se_offline_del = null
  # se_vnic_cooldown - (optional) is a type of number
  se_vnic_cooldown = null
  # secure_channel_cleanup_timeout - (optional) is a type of number
  secure_channel_cleanup_timeout = null
  # secure_channel_controller_token_timeout - (optional) is a type of number
  secure_channel_controller_token_timeout = null
  # secure_channel_se_token_timeout - (optional) is a type of number
  secure_channel_se_token_timeout = null
  # seupgrade_copy_pool_size - (optional) is a type of number
  seupgrade_copy_pool_size = null
  # seupgrade_fabric_pool_size - (optional) is a type of number
  seupgrade_fabric_pool_size = null
  # seupgrade_segroup_min_dead_timeout - (optional) is a type of number
  seupgrade_segroup_min_dead_timeout = null
  # shared_ssl_certificates - (optional) is a type of bool
  shared_ssl_certificates = null
  # ssl_certificate_expiry_warning_days - (optional) is a type of list of number
  ssl_certificate_expiry_warning_days = []
  # unresponsive_se_reboot - (optional) is a type of number
  unresponsive_se_reboot = null
  # upgrade_dns_ttl - (optional) is a type of number
  upgrade_dns_ttl = null
  # upgrade_lease_time - (optional) is a type of number
  upgrade_lease_time = null
  # uuid - (optional) is a type of string
  uuid = null
  # vnic_op_fail_time - (optional) is a type of number
  vnic_op_fail_time = null
  # vs_apic_scaleout_timeout - (optional) is a type of number
  vs_apic_scaleout_timeout = null
  # vs_awaiting_se_timeout - (optional) is a type of number
  vs_awaiting_se_timeout = null
  # vs_key_rotate_period - (optional) is a type of number
  vs_key_rotate_period = null
  # vs_scaleout_ready_check_interval - (optional) is a type of number
  vs_scaleout_ready_check_interval = null
  # vs_se_attach_ip_fail - (optional) is a type of number
  vs_se_attach_ip_fail = null
  # vs_se_bootup_fail - (optional) is a type of number
  vs_se_bootup_fail = null
  # vs_se_create_fail - (optional) is a type of number
  vs_se_create_fail = null
  # vs_se_ping_fail - (optional) is a type of number
  vs_se_ping_fail = null
  # vs_se_vnic_fail - (optional) is a type of number
  vs_se_vnic_fail = null
  # vs_se_vnic_ip_fail - (optional) is a type of number
  vs_se_vnic_ip_fail = null
  # warmstart_se_reconnect_wait_time - (optional) is a type of number
  warmstart_se_reconnect_wait_time = null
  # warmstart_vs_resync_wait_time - (optional) is a type of number
  warmstart_vs_resync_wait_time = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_admin_network_updates" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_ip_forwarding" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_unauthenticated_apis" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_unauthenticated_nodes" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "api_idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "api_perf_logging_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "appviewx_compat_mode" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "attach_ip_retry_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "attach_ip_retry_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "bm_use_ansible" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cleanup_expired_authtoken_timeout_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cleanup_sessions_timeout_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cloud_reconcile" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cluster_ip_gratuitous_arp_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "consistency_check_timeout_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "crashed_se_reboot" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dead_se_detection_timer" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "default_minimum_api_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dns_refresh_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dummy" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_api_sharding" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_memory_balancer" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "fatal_error_lease_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_dead_se_in_grp" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_pcap_per_tenant" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_seq_attach_ip_failures" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_seq_vnic_failures" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "permission_scoped_shared_admin_networks" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "persistence_key_rotate_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "portal_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "process_locked_useraccounts_timeout_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "process_pki_profile_timeout_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "query_host_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "safenet_hsm_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "se_create_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_failover_attempt_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_from_marketplace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "se_offline_del" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "se_vnic_cooldown" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "secure_channel_cleanup_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "secure_channel_controller_token_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "secure_channel_se_token_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "seupgrade_copy_pool_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "seupgrade_fabric_pool_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "seupgrade_segroup_min_dead_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_ssl_certificates" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ssl_certificate_expiry_warning_days" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "unresponsive_se_reboot" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "upgrade_dns_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "upgrade_lease_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vnic_op_fail_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_apic_scaleout_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_awaiting_se_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_key_rotate_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_scaleout_ready_check_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_se_attach_ip_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_se_bootup_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_se_create_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_se_ping_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_se_vnic_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vs_se_vnic_ip_fail" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "warmstart_se_reconnect_wait_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "warmstart_vs_resync_wait_time" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "avi_controllerproperties" "this" {
  # allow_admin_network_updates - (optional) is a type of bool
  allow_admin_network_updates = var.allow_admin_network_updates
  # allow_ip_forwarding - (optional) is a type of bool
  allow_ip_forwarding = var.allow_ip_forwarding
  # allow_unauthenticated_apis - (optional) is a type of bool
  allow_unauthenticated_apis = var.allow_unauthenticated_apis
  # allow_unauthenticated_nodes - (optional) is a type of bool
  allow_unauthenticated_nodes = var.allow_unauthenticated_nodes
  # api_idle_timeout - (optional) is a type of number
  api_idle_timeout = var.api_idle_timeout
  # api_perf_logging_threshold - (optional) is a type of number
  api_perf_logging_threshold = var.api_perf_logging_threshold
  # appviewx_compat_mode - (optional) is a type of bool
  appviewx_compat_mode = var.appviewx_compat_mode
  # attach_ip_retry_interval - (optional) is a type of number
  attach_ip_retry_interval = var.attach_ip_retry_interval
  # attach_ip_retry_limit - (optional) is a type of number
  attach_ip_retry_limit = var.attach_ip_retry_limit
  # bm_use_ansible - (optional) is a type of bool
  bm_use_ansible = var.bm_use_ansible
  # cleanup_expired_authtoken_timeout_period - (optional) is a type of number
  cleanup_expired_authtoken_timeout_period = var.cleanup_expired_authtoken_timeout_period
  # cleanup_sessions_timeout_period - (optional) is a type of number
  cleanup_sessions_timeout_period = var.cleanup_sessions_timeout_period
  # cloud_reconcile - (optional) is a type of bool
  cloud_reconcile = var.cloud_reconcile
  # cluster_ip_gratuitous_arp_period - (optional) is a type of number
  cluster_ip_gratuitous_arp_period = var.cluster_ip_gratuitous_arp_period
  # consistency_check_timeout_period - (optional) is a type of number
  consistency_check_timeout_period = var.consistency_check_timeout_period
  # crashed_se_reboot - (optional) is a type of number
  crashed_se_reboot = var.crashed_se_reboot
  # dead_se_detection_timer - (optional) is a type of number
  dead_se_detection_timer = var.dead_se_detection_timer
  # default_minimum_api_timeout - (optional) is a type of number
  default_minimum_api_timeout = var.default_minimum_api_timeout
  # dns_refresh_period - (optional) is a type of number
  dns_refresh_period = var.dns_refresh_period
  # dummy - (optional) is a type of number
  dummy = var.dummy
  # enable_api_sharding - (optional) is a type of bool
  enable_api_sharding = var.enable_api_sharding
  # enable_memory_balancer - (optional) is a type of bool
  enable_memory_balancer = var.enable_memory_balancer
  # fatal_error_lease_time - (optional) is a type of number
  fatal_error_lease_time = var.fatal_error_lease_time
  # max_dead_se_in_grp - (optional) is a type of number
  max_dead_se_in_grp = var.max_dead_se_in_grp
  # max_pcap_per_tenant - (optional) is a type of number
  max_pcap_per_tenant = var.max_pcap_per_tenant
  # max_seq_attach_ip_failures - (optional) is a type of number
  max_seq_attach_ip_failures = var.max_seq_attach_ip_failures
  # max_seq_vnic_failures - (optional) is a type of number
  max_seq_vnic_failures = var.max_seq_vnic_failures
  # permission_scoped_shared_admin_networks - (optional) is a type of bool
  permission_scoped_shared_admin_networks = var.permission_scoped_shared_admin_networks
  # persistence_key_rotate_period - (optional) is a type of number
  persistence_key_rotate_period = var.persistence_key_rotate_period
  # portal_token - (optional) is a type of string
  portal_token = var.portal_token
  # process_locked_useraccounts_timeout_period - (optional) is a type of number
  process_locked_useraccounts_timeout_period = var.process_locked_useraccounts_timeout_period
  # process_pki_profile_timeout_period - (optional) is a type of number
  process_pki_profile_timeout_period = var.process_pki_profile_timeout_period
  # query_host_fail - (optional) is a type of number
  query_host_fail = var.query_host_fail
  # safenet_hsm_version - (optional) is a type of string
  safenet_hsm_version = var.safenet_hsm_version
  # se_create_timeout - (optional) is a type of number
  se_create_timeout = var.se_create_timeout
  # se_failover_attempt_interval - (optional) is a type of number
  se_failover_attempt_interval = var.se_failover_attempt_interval
  # se_from_marketplace - (optional) is a type of string
  se_from_marketplace = var.se_from_marketplace
  # se_offline_del - (optional) is a type of number
  se_offline_del = var.se_offline_del
  # se_vnic_cooldown - (optional) is a type of number
  se_vnic_cooldown = var.se_vnic_cooldown
  # secure_channel_cleanup_timeout - (optional) is a type of number
  secure_channel_cleanup_timeout = var.secure_channel_cleanup_timeout
  # secure_channel_controller_token_timeout - (optional) is a type of number
  secure_channel_controller_token_timeout = var.secure_channel_controller_token_timeout
  # secure_channel_se_token_timeout - (optional) is a type of number
  secure_channel_se_token_timeout = var.secure_channel_se_token_timeout
  # seupgrade_copy_pool_size - (optional) is a type of number
  seupgrade_copy_pool_size = var.seupgrade_copy_pool_size
  # seupgrade_fabric_pool_size - (optional) is a type of number
  seupgrade_fabric_pool_size = var.seupgrade_fabric_pool_size
  # seupgrade_segroup_min_dead_timeout - (optional) is a type of number
  seupgrade_segroup_min_dead_timeout = var.seupgrade_segroup_min_dead_timeout
  # shared_ssl_certificates - (optional) is a type of bool
  shared_ssl_certificates = var.shared_ssl_certificates
  # ssl_certificate_expiry_warning_days - (optional) is a type of list of number
  ssl_certificate_expiry_warning_days = var.ssl_certificate_expiry_warning_days
  # unresponsive_se_reboot - (optional) is a type of number
  unresponsive_se_reboot = var.unresponsive_se_reboot
  # upgrade_dns_ttl - (optional) is a type of number
  upgrade_dns_ttl = var.upgrade_dns_ttl
  # upgrade_lease_time - (optional) is a type of number
  upgrade_lease_time = var.upgrade_lease_time
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # vnic_op_fail_time - (optional) is a type of number
  vnic_op_fail_time = var.vnic_op_fail_time
  # vs_apic_scaleout_timeout - (optional) is a type of number
  vs_apic_scaleout_timeout = var.vs_apic_scaleout_timeout
  # vs_awaiting_se_timeout - (optional) is a type of number
  vs_awaiting_se_timeout = var.vs_awaiting_se_timeout
  # vs_key_rotate_period - (optional) is a type of number
  vs_key_rotate_period = var.vs_key_rotate_period
  # vs_scaleout_ready_check_interval - (optional) is a type of number
  vs_scaleout_ready_check_interval = var.vs_scaleout_ready_check_interval
  # vs_se_attach_ip_fail - (optional) is a type of number
  vs_se_attach_ip_fail = var.vs_se_attach_ip_fail
  # vs_se_bootup_fail - (optional) is a type of number
  vs_se_bootup_fail = var.vs_se_bootup_fail
  # vs_se_create_fail - (optional) is a type of number
  vs_se_create_fail = var.vs_se_create_fail
  # vs_se_ping_fail - (optional) is a type of number
  vs_se_ping_fail = var.vs_se_ping_fail
  # vs_se_vnic_fail - (optional) is a type of number
  vs_se_vnic_fail = var.vs_se_vnic_fail
  # vs_se_vnic_ip_fail - (optional) is a type of number
  vs_se_vnic_ip_fail = var.vs_se_vnic_ip_fail
  # warmstart_se_reconnect_wait_time - (optional) is a type of number
  warmstart_se_reconnect_wait_time = var.warmstart_se_reconnect_wait_time
  # warmstart_vs_resync_wait_time - (optional) is a type of number
  warmstart_vs_resync_wait_time = var.warmstart_vs_resync_wait_time
}
```

[top](#index)

### Outputs

```terraform
output "dummy" {
  description = "returns a number"
  value       = avi_controllerproperties.this.dummy
}

output "id" {
  description = "returns a string"
  value       = avi_controllerproperties.this.id
}

output "portal_token" {
  description = "returns a string"
  value       = avi_controllerproperties.this.portal_token
}

output "safenet_hsm_version" {
  description = "returns a string"
  value       = avi_controllerproperties.this.safenet_hsm_version
}

output "uuid" {
  description = "returns a string"
  value       = avi_controllerproperties.this.uuid
}

output "this" {
  value = avi_controllerproperties.this
}
```

[top](#index)