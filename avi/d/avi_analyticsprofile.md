# avi_analyticsprofile

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
module "avi_analyticsprofile" {
  source = "./modules/avi/d/avi_analyticsprofile"

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
data "avi_analyticsprofile" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "apdex_response_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.apdex_response_threshold
}

output "apdex_response_tolerated_factor" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.apdex_response_tolerated_factor
}

output "apdex_rtt_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.apdex_rtt_threshold
}

output "apdex_rtt_tolerated_factor" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.apdex_rtt_tolerated_factor
}

output "apdex_rum_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.apdex_rum_threshold
}

output "apdex_rum_tolerated_factor" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.apdex_rum_tolerated_factor
}

output "apdex_server_response_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.apdex_server_response_threshold
}

output "apdex_server_response_tolerated_factor" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.apdex_server_response_tolerated_factor
}

output "apdex_server_rtt_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.apdex_server_rtt_threshold
}

output "apdex_server_rtt_tolerated_factor" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.apdex_server_rtt_tolerated_factor
}

output "client_log_config" {
  description = "returns a set of object"
  value       = data.avi_analyticsprofile.this.client_log_config
}

output "client_log_streaming_config" {
  description = "returns a set of object"
  value       = data.avi_analyticsprofile.this.client_log_streaming_config
}

output "conn_lossy_ooo_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.conn_lossy_ooo_threshold
}

output "conn_lossy_timeo_rexmt_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.conn_lossy_timeo_rexmt_threshold
}

output "conn_lossy_total_rexmt_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.conn_lossy_total_rexmt_threshold
}

output "conn_lossy_zero_win_size_event_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.conn_lossy_zero_win_size_event_threshold
}

output "conn_server_lossy_ooo_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.conn_server_lossy_ooo_threshold
}

output "conn_server_lossy_timeo_rexmt_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.conn_server_lossy_timeo_rexmt_threshold
}

output "conn_server_lossy_total_rexmt_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.conn_server_lossy_total_rexmt_threshold
}

output "conn_server_lossy_zero_win_size_event_threshold" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.conn_server_lossy_zero_win_size_event_threshold
}

output "description" {
  description = "returns a string"
  value       = data.avi_analyticsprofile.this.description
}

output "disable_ondemand_metrics" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.disable_ondemand_metrics
}

output "disable_se_analytics" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.disable_se_analytics
}

output "disable_server_analytics" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.disable_server_analytics
}

output "disable_vs_analytics" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.disable_vs_analytics
}

output "enable_advanced_analytics" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.enable_advanced_analytics
}

output "exclude_client_close_before_request_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_client_close_before_request_as_error
}

output "exclude_dns_policy_drop_as_significant" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_dns_policy_drop_as_significant
}

output "exclude_gs_down_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_gs_down_as_error
}

output "exclude_http_error_codes" {
  description = "returns a list of number"
  value       = data.avi_analyticsprofile.this.exclude_http_error_codes
}

output "exclude_invalid_dns_domain_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_invalid_dns_domain_as_error
}

output "exclude_invalid_dns_query_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_invalid_dns_query_as_error
}

output "exclude_no_dns_record_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_no_dns_record_as_error
}

output "exclude_no_valid_gs_member_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_no_valid_gs_member_as_error
}

output "exclude_persistence_change_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_persistence_change_as_error
}

output "exclude_server_dns_error_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_server_dns_error_as_error
}

output "exclude_server_tcp_reset_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_server_tcp_reset_as_error
}

output "exclude_sip_error_codes" {
  description = "returns a list of number"
  value       = data.avi_analyticsprofile.this.exclude_sip_error_codes
}

output "exclude_syn_retransmit_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_syn_retransmit_as_error
}

output "exclude_tcp_reset_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_tcp_reset_as_error
}

output "exclude_unsupported_dns_query_as_error" {
  description = "returns a bool"
  value       = data.avi_analyticsprofile.this.exclude_unsupported_dns_query_as_error
}

output "healthscore_max_server_limit" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.healthscore_max_server_limit
}

output "hs_event_throttle_window" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_event_throttle_window
}

output "hs_max_anomaly_penalty" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_max_anomaly_penalty
}

output "hs_max_resources_penalty" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_max_resources_penalty
}

output "hs_max_security_penalty" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_max_security_penalty
}

output "hs_min_dos_rate" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_min_dos_rate
}

output "hs_performance_boost" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_performance_boost
}

output "hs_pscore_traffic_threshold_l4_client" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_pscore_traffic_threshold_l4_client
}

output "hs_pscore_traffic_threshold_l4_server" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_pscore_traffic_threshold_l4_server
}

output "hs_security_certscore_expired" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_certscore_expired
}

output "hs_security_certscore_gt30d" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_certscore_gt30d
}

output "hs_security_certscore_le07d" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_certscore_le07d
}

output "hs_security_certscore_le30d" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_certscore_le30d
}

output "hs_security_chain_invalidity_penalty" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_chain_invalidity_penalty
}

output "hs_security_cipherscore_eq000b" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_cipherscore_eq000b
}

output "hs_security_cipherscore_ge128b" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_cipherscore_ge128b
}

output "hs_security_cipherscore_lt128b" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_cipherscore_lt128b
}

output "hs_security_encalgo_score_none" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_encalgo_score_none
}

output "hs_security_encalgo_score_rc4" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_encalgo_score_rc4
}

output "hs_security_hsts_penalty" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_hsts_penalty
}

output "hs_security_nonpfs_penalty" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_nonpfs_penalty
}

output "hs_security_selfsignedcert_penalty" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_selfsignedcert_penalty
}

output "hs_security_ssl30_score" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_ssl30_score
}

output "hs_security_tls10_score" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_tls10_score
}

output "hs_security_tls11_score" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_tls11_score
}

output "hs_security_tls12_score" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_tls12_score
}

output "hs_security_weak_signature_algo_penalty" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.hs_security_weak_signature_algo_penalty
}

output "id" {
  description = "returns a string"
  value       = data.avi_analyticsprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_analyticsprofile.this.name
}

output "ondemand_metrics_idle_timeout" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.ondemand_metrics_idle_timeout
}

output "ranges" {
  description = "returns a list of object"
  value       = data.avi_analyticsprofile.this.ranges
}

output "resp_code_block" {
  description = "returns a list of string"
  value       = data.avi_analyticsprofile.this.resp_code_block
}

output "sensitive_log_profile" {
  description = "returns a set of object"
  value       = data.avi_analyticsprofile.this.sensitive_log_profile
}

output "sip_log_depth" {
  description = "returns a number"
  value       = data.avi_analyticsprofile.this.sip_log_depth
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_analyticsprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_analyticsprofile.this.uuid
}

output "this" {
  value = avi_analyticsprofile.this
}
```

[top](#index)