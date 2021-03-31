# avi_virtualservice

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
module "avi_virtualservice" {
  source = "./modules/avi/d/avi_virtualservice"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_virtualservice" "this" {
  cloud_ref  = var.cloud_ref
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "active_standby_se_tag" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.active_standby_se_tag
}

output "allow_invalid_client_cert" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.allow_invalid_client_cert
}

output "analytics_policy" {
  description = "returns a set of object"
  value       = data.avi_virtualservice.this.analytics_policy
}

output "analytics_profile_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.analytics_profile_ref
}

output "apic_contract_graph" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.apic_contract_graph
}

output "application_profile_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.application_profile_ref
}

output "bulk_sync_kvcache" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.bulk_sync_kvcache
}

output "client_auth" {
  description = "returns a set of object"
  value       = data.avi_virtualservice.this.client_auth
}

output "close_client_conn_on_config_update" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.close_client_conn_on_config_update
}

output "cloud_config_cksum" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.cloud_config_cksum
}

output "cloud_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.cloud_ref
}

output "cloud_type" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.cloud_type
}

output "connections_rate_limit" {
  description = "returns a set of object"
  value       = data.avi_virtualservice.this.connections_rate_limit
}

output "content_rewrite" {
  description = "returns a set of object"
  value       = data.avi_virtualservice.this.content_rewrite
}

output "created_by" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.created_by
}

output "delay_fairness" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.delay_fairness
}

output "description" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.description
}

output "dns_info" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.dns_info
}

output "dns_policies" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.dns_policies
}

output "east_west_placement" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.east_west_placement
}

output "enable_autogw" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.enable_autogw
}

output "enable_rhi" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.enable_rhi
}

output "enable_rhi_snat" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.enable_rhi_snat
}

output "enabled" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.enabled
}

output "error_page_profile_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.error_page_profile_ref
}

output "flow_dist" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.flow_dist
}

output "flow_label_type" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.flow_label_type
}

output "fqdn" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.fqdn
}

output "host_name_xlate" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.host_name_xlate
}

output "http_policies" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.http_policies
}

output "id" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.id
}

output "ign_pool_net_reach" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.ign_pool_net_reach
}

output "l4_policies" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.l4_policies
}

output "limit_doser" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.limit_doser
}

output "max_cps_per_client" {
  description = "returns a number"
  value       = data.avi_virtualservice.this.max_cps_per_client
}

output "microservice_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.microservice_ref
}

output "min_pools_up" {
  description = "returns a number"
  value       = data.avi_virtualservice.this.min_pools_up
}

output "name" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.name
}

output "network_profile_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.network_profile_ref
}

output "network_security_policy_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.network_security_policy_ref
}

output "nsx_securitygroup" {
  description = "returns a list of string"
  value       = data.avi_virtualservice.this.nsx_securitygroup
}

output "performance_limits" {
  description = "returns a set of object"
  value       = data.avi_virtualservice.this.performance_limits
}

output "pool_group_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.pool_group_ref
}

output "pool_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.pool_ref
}

output "remove_listening_port_on_vs_down" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.remove_listening_port_on_vs_down
}

output "requests_rate_limit" {
  description = "returns a set of object"
  value       = data.avi_virtualservice.this.requests_rate_limit
}

output "saml_sp_config" {
  description = "returns a set of object"
  value       = data.avi_virtualservice.this.saml_sp_config
}

output "scaleout_ecmp" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.scaleout_ecmp
}

output "se_group_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.se_group_ref
}

output "security_policy_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.security_policy_ref
}

output "server_network_profile_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.server_network_profile_ref
}

output "service_metadata" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.service_metadata
}

output "service_pool_select" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.service_pool_select
}

output "services" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.services
}

output "sideband_profile" {
  description = "returns a set of object"
  value       = data.avi_virtualservice.this.sideband_profile
}

output "snat_ip" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.snat_ip
}

output "ssl_key_and_certificate_refs" {
  description = "returns a list of string"
  value       = data.avi_virtualservice.this.ssl_key_and_certificate_refs
}

output "ssl_profile_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.ssl_profile_ref
}

output "ssl_profile_selectors" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.ssl_profile_selectors
}

output "ssl_sess_cache_avg_size" {
  description = "returns a number"
  value       = data.avi_virtualservice.this.ssl_sess_cache_avg_size
}

output "sso_policy_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.sso_policy_ref
}

output "static_dns_records" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.static_dns_records
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.tenant_ref
}

output "test_se_datastore_level_1_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.test_se_datastore_level_1_ref
}

output "topology_policies" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.topology_policies
}

output "traffic_clone_profile_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.traffic_clone_profile_ref
}

output "traffic_enabled" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.traffic_enabled
}

output "type" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.type
}

output "use_bridge_ip_as_vip" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.use_bridge_ip_as_vip
}

output "use_vip_as_snat" {
  description = "returns a bool"
  value       = data.avi_virtualservice.this.use_vip_as_snat
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.uuid
}

output "vh_domain_name" {
  description = "returns a list of string"
  value       = data.avi_virtualservice.this.vh_domain_name
}

output "vh_parent_vs_uuid" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.vh_parent_vs_uuid
}

output "vip" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.vip
}

output "vrf_context_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.vrf_context_ref
}

output "vs_datascripts" {
  description = "returns a list of object"
  value       = data.avi_virtualservice.this.vs_datascripts
}

output "vsvip_cloud_config_cksum" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.vsvip_cloud_config_cksum
}

output "vsvip_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.vsvip_ref
}

output "waf_policy_ref" {
  description = "returns a string"
  value       = data.avi_virtualservice.this.waf_policy_ref
}

output "weight" {
  description = "returns a number"
  value       = data.avi_virtualservice.this.weight
}

output "this" {
  value = avi_virtualservice.this
}
```

[top](#index)