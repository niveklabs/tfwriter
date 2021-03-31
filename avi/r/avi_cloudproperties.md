# avi_cloudproperties

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
module "avi_cloudproperties" {
  source = "./modules/avi/r/avi_cloudproperties"

  # cc_vtypes - (optional) is a type of list of string
  cc_vtypes = []
  # uuid - (optional) is a type of string
  uuid = null

  cc_props = [{
    rpc_poll_interval = null
    rpc_queue_size    = null
  }]

  hyp_props = [{
    htype           = null
    max_ips_per_nic = null
    max_nics        = null
  }]

  info = [{
    cca_props = [{
      async_retries        = null
      async_retries_delay  = null
      poll_duration_target = null
      poll_fast_target     = null
      poll_slow_target     = null
      vnic_retries         = null
      vnic_retries_delay   = null
    }]
    controller_props = [{
      allow_admin_network_updates                = null
      allow_ip_forwarding                        = null
      allow_unauthenticated_apis                 = null
      allow_unauthenticated_nodes                = null
      api_idle_timeout                           = null
      api_perf_logging_threshold                 = null
      appviewx_compat_mode                       = null
      attach_ip_retry_interval                   = null
      attach_ip_retry_limit                      = null
      bm_use_ansible                             = null
      cleanup_expired_authtoken_timeout_period   = null
      cleanup_sessions_timeout_period            = null
      cloud_reconcile                            = null
      cluster_ip_gratuitous_arp_period           = null
      consistency_check_timeout_period           = null
      crashed_se_reboot                          = null
      dead_se_detection_timer                    = null
      default_minimum_api_timeout                = null
      dns_refresh_period                         = null
      dummy                                      = null
      enable_api_sharding                        = null
      enable_memory_balancer                     = null
      fatal_error_lease_time                     = null
      max_dead_se_in_grp                         = null
      max_pcap_per_tenant                        = null
      max_seq_attach_ip_failures                 = null
      max_seq_vnic_failures                      = null
      permission_scoped_shared_admin_networks    = null
      persistence_key_rotate_period              = null
      portal_token                               = null
      process_locked_useraccounts_timeout_period = null
      process_pki_profile_timeout_period         = null
      query_host_fail                            = null
      safenet_hsm_version                        = null
      se_create_timeout                          = null
      se_failover_attempt_interval               = null
      se_from_marketplace                        = null
      se_offline_del                             = null
      se_vnic_cooldown                           = null
      secure_channel_cleanup_timeout             = null
      secure_channel_controller_token_timeout    = null
      secure_channel_se_token_timeout            = null
      seupgrade_copy_pool_size                   = null
      seupgrade_fabric_pool_size                 = null
      seupgrade_segroup_min_dead_timeout         = null
      shared_ssl_certificates                    = null
      ssl_certificate_expiry_warning_days        = []
      unresponsive_se_reboot                     = null
      upgrade_dns_ttl                            = null
      upgrade_lease_time                         = null
      uuid                                       = null
      vnic_op_fail_time                          = null
      vs_apic_scaleout_timeout                   = null
      vs_awaiting_se_timeout                     = null
      vs_key_rotate_period                       = null
      vs_scaleout_ready_check_interval           = null
      vs_se_attach_ip_fail                       = null
      vs_se_bootup_fail                          = null
      vs_se_create_fail                          = null
      vs_se_ping_fail                            = null
      vs_se_vnic_fail                            = null
      vs_se_vnic_ip_fail                         = null
      warmstart_se_reconnect_wait_time           = null
      warmstart_vs_resync_wait_time              = null
    }]
    flavor_props = [{
      cost             = null
      disk_gb          = null
      enhanced_nw      = null
      id               = null
      is_recommended   = null
      max_ip6s_per_nic = null
      max_ips_per_nic  = null
      max_nics         = null
      meta = [{
        key   = null
        value = null
      }]
      name   = null
      public = null
      ram_mb = null
      vcpus  = null
    }]
    flavor_regex_filter = null
    htypes              = []
    vtype               = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cc_vtypes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cc_props" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      rpc_poll_interval = number
      rpc_queue_size    = number
    }
  ))
  default = []
}

variable "hyp_props" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      htype           = string
      max_ips_per_nic = number
      max_nics        = number
    }
  ))
  default = []
}

variable "info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cca_props = set(object(
        {
          async_retries        = number
          async_retries_delay  = number
          poll_duration_target = number
          poll_fast_target     = number
          poll_slow_target     = number
          vnic_retries         = number
          vnic_retries_delay   = number
        }
      ))
      controller_props = set(object(
        {
          allow_admin_network_updates                = bool
          allow_ip_forwarding                        = bool
          allow_unauthenticated_apis                 = bool
          allow_unauthenticated_nodes                = bool
          api_idle_timeout                           = number
          api_perf_logging_threshold                 = number
          appviewx_compat_mode                       = bool
          attach_ip_retry_interval                   = number
          attach_ip_retry_limit                      = number
          bm_use_ansible                             = bool
          cleanup_expired_authtoken_timeout_period   = number
          cleanup_sessions_timeout_period            = number
          cloud_reconcile                            = bool
          cluster_ip_gratuitous_arp_period           = number
          consistency_check_timeout_period           = number
          crashed_se_reboot                          = number
          dead_se_detection_timer                    = number
          default_minimum_api_timeout                = number
          dns_refresh_period                         = number
          dummy                                      = number
          enable_api_sharding                        = bool
          enable_memory_balancer                     = bool
          fatal_error_lease_time                     = number
          max_dead_se_in_grp                         = number
          max_pcap_per_tenant                        = number
          max_seq_attach_ip_failures                 = number
          max_seq_vnic_failures                      = number
          permission_scoped_shared_admin_networks    = bool
          persistence_key_rotate_period              = number
          portal_token                               = string
          process_locked_useraccounts_timeout_period = number
          process_pki_profile_timeout_period         = number
          query_host_fail                            = number
          safenet_hsm_version                        = string
          se_create_timeout                          = number
          se_failover_attempt_interval               = number
          se_from_marketplace                        = string
          se_offline_del                             = number
          se_vnic_cooldown                           = number
          secure_channel_cleanup_timeout             = number
          secure_channel_controller_token_timeout    = number
          secure_channel_se_token_timeout            = number
          seupgrade_copy_pool_size                   = number
          seupgrade_fabric_pool_size                 = number
          seupgrade_segroup_min_dead_timeout         = number
          shared_ssl_certificates                    = bool
          ssl_certificate_expiry_warning_days        = list(number)
          unresponsive_se_reboot                     = number
          upgrade_dns_ttl                            = number
          upgrade_lease_time                         = number
          uuid                                       = string
          vnic_op_fail_time                          = number
          vs_apic_scaleout_timeout                   = number
          vs_awaiting_se_timeout                     = number
          vs_key_rotate_period                       = number
          vs_scaleout_ready_check_interval           = number
          vs_se_attach_ip_fail                       = number
          vs_se_bootup_fail                          = number
          vs_se_create_fail                          = number
          vs_se_ping_fail                            = number
          vs_se_vnic_fail                            = number
          vs_se_vnic_ip_fail                         = number
          warmstart_se_reconnect_wait_time           = number
          warmstart_vs_resync_wait_time              = number
        }
      ))
      flavor_props = list(object(
        {
          cost             = string
          disk_gb          = number
          enhanced_nw      = bool
          id               = string
          is_recommended   = bool
          max_ip6s_per_nic = number
          max_ips_per_nic  = number
          max_nics         = number
          meta = list(object(
            {
              key   = string
              value = string
            }
          ))
          name   = string
          public = bool
          ram_mb = number
          vcpus  = number
        }
      ))
      flavor_regex_filter = string
      htypes              = list(string)
      vtype               = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_cloudproperties" "this" {
  cc_vtypes = var.cc_vtypes
  uuid      = var.uuid

  dynamic "cc_props" {
    for_each = var.cc_props
    content {
      rpc_poll_interval = cc_props.value["rpc_poll_interval"]
      rpc_queue_size    = cc_props.value["rpc_queue_size"]
    }
  }

  dynamic "hyp_props" {
    for_each = var.hyp_props
    content {
      htype           = hyp_props.value["htype"]
      max_ips_per_nic = hyp_props.value["max_ips_per_nic"]
      max_nics        = hyp_props.value["max_nics"]
    }
  }

  dynamic "info" {
    for_each = var.info
    content {
      flavor_regex_filter = info.value["flavor_regex_filter"]
      htypes              = info.value["htypes"]
      vtype               = info.value["vtype"]

      dynamic "cca_props" {
        for_each = info.value.cca_props
        content {
          async_retries        = cca_props.value["async_retries"]
          async_retries_delay  = cca_props.value["async_retries_delay"]
          poll_duration_target = cca_props.value["poll_duration_target"]
          poll_fast_target     = cca_props.value["poll_fast_target"]
          poll_slow_target     = cca_props.value["poll_slow_target"]
          vnic_retries         = cca_props.value["vnic_retries"]
          vnic_retries_delay   = cca_props.value["vnic_retries_delay"]
        }
      }

      dynamic "controller_props" {
        for_each = info.value.controller_props
        content {
          allow_admin_network_updates                = controller_props.value["allow_admin_network_updates"]
          allow_ip_forwarding                        = controller_props.value["allow_ip_forwarding"]
          allow_unauthenticated_apis                 = controller_props.value["allow_unauthenticated_apis"]
          allow_unauthenticated_nodes                = controller_props.value["allow_unauthenticated_nodes"]
          api_idle_timeout                           = controller_props.value["api_idle_timeout"]
          api_perf_logging_threshold                 = controller_props.value["api_perf_logging_threshold"]
          appviewx_compat_mode                       = controller_props.value["appviewx_compat_mode"]
          attach_ip_retry_interval                   = controller_props.value["attach_ip_retry_interval"]
          attach_ip_retry_limit                      = controller_props.value["attach_ip_retry_limit"]
          bm_use_ansible                             = controller_props.value["bm_use_ansible"]
          cleanup_expired_authtoken_timeout_period   = controller_props.value["cleanup_expired_authtoken_timeout_period"]
          cleanup_sessions_timeout_period            = controller_props.value["cleanup_sessions_timeout_period"]
          cloud_reconcile                            = controller_props.value["cloud_reconcile"]
          cluster_ip_gratuitous_arp_period           = controller_props.value["cluster_ip_gratuitous_arp_period"]
          consistency_check_timeout_period           = controller_props.value["consistency_check_timeout_period"]
          crashed_se_reboot                          = controller_props.value["crashed_se_reboot"]
          dead_se_detection_timer                    = controller_props.value["dead_se_detection_timer"]
          default_minimum_api_timeout                = controller_props.value["default_minimum_api_timeout"]
          dns_refresh_period                         = controller_props.value["dns_refresh_period"]
          dummy                                      = controller_props.value["dummy"]
          enable_api_sharding                        = controller_props.value["enable_api_sharding"]
          enable_memory_balancer                     = controller_props.value["enable_memory_balancer"]
          fatal_error_lease_time                     = controller_props.value["fatal_error_lease_time"]
          max_dead_se_in_grp                         = controller_props.value["max_dead_se_in_grp"]
          max_pcap_per_tenant                        = controller_props.value["max_pcap_per_tenant"]
          max_seq_attach_ip_failures                 = controller_props.value["max_seq_attach_ip_failures"]
          max_seq_vnic_failures                      = controller_props.value["max_seq_vnic_failures"]
          permission_scoped_shared_admin_networks    = controller_props.value["permission_scoped_shared_admin_networks"]
          persistence_key_rotate_period              = controller_props.value["persistence_key_rotate_period"]
          portal_token                               = controller_props.value["portal_token"]
          process_locked_useraccounts_timeout_period = controller_props.value["process_locked_useraccounts_timeout_period"]
          process_pki_profile_timeout_period         = controller_props.value["process_pki_profile_timeout_period"]
          query_host_fail                            = controller_props.value["query_host_fail"]
          safenet_hsm_version                        = controller_props.value["safenet_hsm_version"]
          se_create_timeout                          = controller_props.value["se_create_timeout"]
          se_failover_attempt_interval               = controller_props.value["se_failover_attempt_interval"]
          se_from_marketplace                        = controller_props.value["se_from_marketplace"]
          se_offline_del                             = controller_props.value["se_offline_del"]
          se_vnic_cooldown                           = controller_props.value["se_vnic_cooldown"]
          secure_channel_cleanup_timeout             = controller_props.value["secure_channel_cleanup_timeout"]
          secure_channel_controller_token_timeout    = controller_props.value["secure_channel_controller_token_timeout"]
          secure_channel_se_token_timeout            = controller_props.value["secure_channel_se_token_timeout"]
          seupgrade_copy_pool_size                   = controller_props.value["seupgrade_copy_pool_size"]
          seupgrade_fabric_pool_size                 = controller_props.value["seupgrade_fabric_pool_size"]
          seupgrade_segroup_min_dead_timeout         = controller_props.value["seupgrade_segroup_min_dead_timeout"]
          shared_ssl_certificates                    = controller_props.value["shared_ssl_certificates"]
          ssl_certificate_expiry_warning_days        = controller_props.value["ssl_certificate_expiry_warning_days"]
          unresponsive_se_reboot                     = controller_props.value["unresponsive_se_reboot"]
          upgrade_dns_ttl                            = controller_props.value["upgrade_dns_ttl"]
          upgrade_lease_time                         = controller_props.value["upgrade_lease_time"]
          uuid                                       = controller_props.value["uuid"]
          vnic_op_fail_time                          = controller_props.value["vnic_op_fail_time"]
          vs_apic_scaleout_timeout                   = controller_props.value["vs_apic_scaleout_timeout"]
          vs_awaiting_se_timeout                     = controller_props.value["vs_awaiting_se_timeout"]
          vs_key_rotate_period                       = controller_props.value["vs_key_rotate_period"]
          vs_scaleout_ready_check_interval           = controller_props.value["vs_scaleout_ready_check_interval"]
          vs_se_attach_ip_fail                       = controller_props.value["vs_se_attach_ip_fail"]
          vs_se_bootup_fail                          = controller_props.value["vs_se_bootup_fail"]
          vs_se_create_fail                          = controller_props.value["vs_se_create_fail"]
          vs_se_ping_fail                            = controller_props.value["vs_se_ping_fail"]
          vs_se_vnic_fail                            = controller_props.value["vs_se_vnic_fail"]
          vs_se_vnic_ip_fail                         = controller_props.value["vs_se_vnic_ip_fail"]
          warmstart_se_reconnect_wait_time           = controller_props.value["warmstart_se_reconnect_wait_time"]
          warmstart_vs_resync_wait_time              = controller_props.value["warmstart_vs_resync_wait_time"]
        }
      }

      dynamic "flavor_props" {
        for_each = info.value.flavor_props
        content {
          cost             = flavor_props.value["cost"]
          disk_gb          = flavor_props.value["disk_gb"]
          enhanced_nw      = flavor_props.value["enhanced_nw"]
          id               = flavor_props.value["id"]
          is_recommended   = flavor_props.value["is_recommended"]
          max_ip6s_per_nic = flavor_props.value["max_ip6s_per_nic"]
          max_ips_per_nic  = flavor_props.value["max_ips_per_nic"]
          max_nics         = flavor_props.value["max_nics"]
          name             = flavor_props.value["name"]
          public           = flavor_props.value["public"]
          ram_mb           = flavor_props.value["ram_mb"]
          vcpus            = flavor_props.value["vcpus"]

          dynamic "meta" {
            for_each = flavor_props.value.meta
            content {
              key   = meta.value["key"]
              value = meta.value["value"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = avi_cloudproperties.this.id
}

output "uuid" {
  description = "returns a string"
  value       = avi_cloudproperties.this.uuid
}

output "this" {
  value = avi_cloudproperties.this
}
```

[top](#index)