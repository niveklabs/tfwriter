# avi_pool

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
module "avi_pool" {
  source = "./modules/avi/d/avi_pool"

  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # ignore_servers - (optional) is a type of bool
  ignore_servers = null
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

variable "ignore_servers" {
  description = "(optional)"
  type        = bool
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
data "avi_pool" "this" {
  cloud_ref      = var.cloud_ref
  ignore_servers = var.ignore_servers
  name           = var.name
  tenant_ref     = var.tenant_ref
  uuid           = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "analytics_policy" {
  description = "returns a set of object"
  value       = data.avi_pool.this.analytics_policy
}

output "analytics_profile_ref" {
  description = "returns a string"
  value       = data.avi_pool.this.analytics_profile_ref
}

output "apic_epg_name" {
  description = "returns a string"
  value       = data.avi_pool.this.apic_epg_name
}

output "application_persistence_profile_ref" {
  description = "returns a string"
  value       = data.avi_pool.this.application_persistence_profile_ref
}

output "autoscale_launch_config_ref" {
  description = "returns a string"
  value       = data.avi_pool.this.autoscale_launch_config_ref
}

output "autoscale_networks" {
  description = "returns a list of string"
  value       = data.avi_pool.this.autoscale_networks
}

output "autoscale_policy_ref" {
  description = "returns a string"
  value       = data.avi_pool.this.autoscale_policy_ref
}

output "capacity_estimation" {
  description = "returns a bool"
  value       = data.avi_pool.this.capacity_estimation
}

output "capacity_estimation_ttfb_thresh" {
  description = "returns a number"
  value       = data.avi_pool.this.capacity_estimation_ttfb_thresh
}

output "cloud_config_cksum" {
  description = "returns a string"
  value       = data.avi_pool.this.cloud_config_cksum
}

output "cloud_ref" {
  description = "returns a string"
  value       = data.avi_pool.this.cloud_ref
}

output "conn_pool_properties" {
  description = "returns a set of object"
  value       = data.avi_pool.this.conn_pool_properties
}

output "connection_ramp_duration" {
  description = "returns a number"
  value       = data.avi_pool.this.connection_ramp_duration
}

output "created_by" {
  description = "returns a string"
  value       = data.avi_pool.this.created_by
}

output "default_server_port" {
  description = "returns a number"
  value       = data.avi_pool.this.default_server_port
}

output "delete_server_on_dns_refresh" {
  description = "returns a bool"
  value       = data.avi_pool.this.delete_server_on_dns_refresh
}

output "description" {
  description = "returns a string"
  value       = data.avi_pool.this.description
}

output "domain_name" {
  description = "returns a list of string"
  value       = data.avi_pool.this.domain_name
}

output "east_west" {
  description = "returns a bool"
  value       = data.avi_pool.this.east_west
}

output "enabled" {
  description = "returns a bool"
  value       = data.avi_pool.this.enabled
}

output "external_autoscale_groups" {
  description = "returns a list of string"
  value       = data.avi_pool.this.external_autoscale_groups
}

output "fail_action" {
  description = "returns a set of object"
  value       = data.avi_pool.this.fail_action
}

output "fewest_tasks_feedback_delay" {
  description = "returns a number"
  value       = data.avi_pool.this.fewest_tasks_feedback_delay
}

output "graceful_disable_timeout" {
  description = "returns a number"
  value       = data.avi_pool.this.graceful_disable_timeout
}

output "health_monitor_refs" {
  description = "returns a list of string"
  value       = data.avi_pool.this.health_monitor_refs
}

output "host_check_enabled" {
  description = "returns a bool"
  value       = data.avi_pool.this.host_check_enabled
}

output "id" {
  description = "returns a string"
  value       = data.avi_pool.this.id
}

output "inline_health_monitor" {
  description = "returns a bool"
  value       = data.avi_pool.this.inline_health_monitor
}

output "ipaddrgroup_ref" {
  description = "returns a string"
  value       = data.avi_pool.this.ipaddrgroup_ref
}

output "lb_algorithm" {
  description = "returns a string"
  value       = data.avi_pool.this.lb_algorithm
}

output "lb_algorithm_consistent_hash_hdr" {
  description = "returns a string"
  value       = data.avi_pool.this.lb_algorithm_consistent_hash_hdr
}

output "lb_algorithm_core_nonaffinity" {
  description = "returns a number"
  value       = data.avi_pool.this.lb_algorithm_core_nonaffinity
}

output "lb_algorithm_hash" {
  description = "returns a string"
  value       = data.avi_pool.this.lb_algorithm_hash
}

output "lookup_server_by_name" {
  description = "returns a bool"
  value       = data.avi_pool.this.lookup_server_by_name
}

output "max_concurrent_connections_per_server" {
  description = "returns a number"
  value       = data.avi_pool.this.max_concurrent_connections_per_server
}

output "max_conn_rate_per_server" {
  description = "returns a set of object"
  value       = data.avi_pool.this.max_conn_rate_per_server
}

output "min_health_monitors_up" {
  description = "returns a number"
  value       = data.avi_pool.this.min_health_monitors_up
}

output "min_servers_up" {
  description = "returns a number"
  value       = data.avi_pool.this.min_servers_up
}

output "name" {
  description = "returns a string"
  value       = data.avi_pool.this.name
}

output "networks" {
  description = "returns a list of object"
  value       = data.avi_pool.this.networks
}

output "nsx_securitygroup" {
  description = "returns a list of string"
  value       = data.avi_pool.this.nsx_securitygroup
}

output "pki_profile_ref" {
  description = "returns a string"
  value       = data.avi_pool.this.pki_profile_ref
}

output "placement_networks" {
  description = "returns a list of object"
  value       = data.avi_pool.this.placement_networks
}

output "request_queue_depth" {
  description = "returns a number"
  value       = data.avi_pool.this.request_queue_depth
}

output "request_queue_enabled" {
  description = "returns a bool"
  value       = data.avi_pool.this.request_queue_enabled
}

output "rewrite_host_header_to_server_name" {
  description = "returns a bool"
  value       = data.avi_pool.this.rewrite_host_header_to_server_name
}

output "rewrite_host_header_to_sni" {
  description = "returns a bool"
  value       = data.avi_pool.this.rewrite_host_header_to_sni
}

output "server_name" {
  description = "returns a string"
  value       = data.avi_pool.this.server_name
}

output "server_reselect" {
  description = "returns a set of object"
  value       = data.avi_pool.this.server_reselect
}

output "server_timeout" {
  description = "returns a number"
  value       = data.avi_pool.this.server_timeout
}

output "servers" {
  description = "returns a list of object"
  value       = data.avi_pool.this.servers
}

output "service_metadata" {
  description = "returns a string"
  value       = data.avi_pool.this.service_metadata
}

output "sni_enabled" {
  description = "returns a bool"
  value       = data.avi_pool.this.sni_enabled
}

output "ssl_key_and_certificate_ref" {
  description = "returns a string"
  value       = data.avi_pool.this.ssl_key_and_certificate_ref
}

output "ssl_profile_ref" {
  description = "returns a string"
  value       = data.avi_pool.this.ssl_profile_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_pool.this.tenant_ref
}

output "use_service_port" {
  description = "returns a bool"
  value       = data.avi_pool.this.use_service_port
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_pool.this.uuid
}

output "vrf_ref" {
  description = "returns a string"
  value       = data.avi_pool.this.vrf_ref
}

output "this" {
  value = avi_pool.this
}
```

[top](#index)