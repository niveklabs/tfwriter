# avi_analyticsprofile

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
module "avi_analyticsprofile" {
  source = "./modules/avi/r/avi_analyticsprofile"

  # apdex_response_threshold - (optional) is a type of number
  apdex_response_threshold = null
  # apdex_response_tolerated_factor - (optional) is a type of number
  apdex_response_tolerated_factor = null
  # apdex_rtt_threshold - (optional) is a type of number
  apdex_rtt_threshold = null
  # apdex_rtt_tolerated_factor - (optional) is a type of number
  apdex_rtt_tolerated_factor = null
  # apdex_rum_threshold - (optional) is a type of number
  apdex_rum_threshold = null
  # apdex_rum_tolerated_factor - (optional) is a type of number
  apdex_rum_tolerated_factor = null
  # apdex_server_response_threshold - (optional) is a type of number
  apdex_server_response_threshold = null
  # apdex_server_response_tolerated_factor - (optional) is a type of number
  apdex_server_response_tolerated_factor = null
  # apdex_server_rtt_threshold - (optional) is a type of number
  apdex_server_rtt_threshold = null
  # apdex_server_rtt_tolerated_factor - (optional) is a type of number
  apdex_server_rtt_tolerated_factor = null
  # conn_lossy_ooo_threshold - (optional) is a type of number
  conn_lossy_ooo_threshold = null
  # conn_lossy_timeo_rexmt_threshold - (optional) is a type of number
  conn_lossy_timeo_rexmt_threshold = null
  # conn_lossy_total_rexmt_threshold - (optional) is a type of number
  conn_lossy_total_rexmt_threshold = null
  # conn_lossy_zero_win_size_event_threshold - (optional) is a type of number
  conn_lossy_zero_win_size_event_threshold = null
  # conn_server_lossy_ooo_threshold - (optional) is a type of number
  conn_server_lossy_ooo_threshold = null
  # conn_server_lossy_timeo_rexmt_threshold - (optional) is a type of number
  conn_server_lossy_timeo_rexmt_threshold = null
  # conn_server_lossy_total_rexmt_threshold - (optional) is a type of number
  conn_server_lossy_total_rexmt_threshold = null
  # conn_server_lossy_zero_win_size_event_threshold - (optional) is a type of number
  conn_server_lossy_zero_win_size_event_threshold = null
  # description - (optional) is a type of string
  description = null
  # disable_ondemand_metrics - (optional) is a type of bool
  disable_ondemand_metrics = null
  # disable_se_analytics - (optional) is a type of bool
  disable_se_analytics = null
  # disable_server_analytics - (optional) is a type of bool
  disable_server_analytics = null
  # disable_vs_analytics - (optional) is a type of bool
  disable_vs_analytics = null
  # enable_advanced_analytics - (optional) is a type of bool
  enable_advanced_analytics = null
  # exclude_client_close_before_request_as_error - (optional) is a type of bool
  exclude_client_close_before_request_as_error = null
  # exclude_dns_policy_drop_as_significant - (optional) is a type of bool
  exclude_dns_policy_drop_as_significant = null
  # exclude_gs_down_as_error - (optional) is a type of bool
  exclude_gs_down_as_error = null
  # exclude_http_error_codes - (optional) is a type of list of number
  exclude_http_error_codes = []
  # exclude_invalid_dns_domain_as_error - (optional) is a type of bool
  exclude_invalid_dns_domain_as_error = null
  # exclude_invalid_dns_query_as_error - (optional) is a type of bool
  exclude_invalid_dns_query_as_error = null
  # exclude_no_dns_record_as_error - (optional) is a type of bool
  exclude_no_dns_record_as_error = null
  # exclude_no_valid_gs_member_as_error - (optional) is a type of bool
  exclude_no_valid_gs_member_as_error = null
  # exclude_persistence_change_as_error - (optional) is a type of bool
  exclude_persistence_change_as_error = null
  # exclude_server_dns_error_as_error - (optional) is a type of bool
  exclude_server_dns_error_as_error = null
  # exclude_server_tcp_reset_as_error - (optional) is a type of bool
  exclude_server_tcp_reset_as_error = null
  # exclude_sip_error_codes - (optional) is a type of list of number
  exclude_sip_error_codes = []
  # exclude_syn_retransmit_as_error - (optional) is a type of bool
  exclude_syn_retransmit_as_error = null
  # exclude_tcp_reset_as_error - (optional) is a type of bool
  exclude_tcp_reset_as_error = null
  # exclude_unsupported_dns_query_as_error - (optional) is a type of bool
  exclude_unsupported_dns_query_as_error = null
  # healthscore_max_server_limit - (optional) is a type of number
  healthscore_max_server_limit = null
  # hs_event_throttle_window - (optional) is a type of number
  hs_event_throttle_window = null
  # hs_max_anomaly_penalty - (optional) is a type of number
  hs_max_anomaly_penalty = null
  # hs_max_resources_penalty - (optional) is a type of number
  hs_max_resources_penalty = null
  # hs_max_security_penalty - (optional) is a type of number
  hs_max_security_penalty = null
  # hs_min_dos_rate - (optional) is a type of number
  hs_min_dos_rate = null
  # hs_performance_boost - (optional) is a type of number
  hs_performance_boost = null
  # hs_pscore_traffic_threshold_l4_client - (optional) is a type of number
  hs_pscore_traffic_threshold_l4_client = null
  # hs_pscore_traffic_threshold_l4_server - (optional) is a type of number
  hs_pscore_traffic_threshold_l4_server = null
  # hs_security_certscore_expired - (optional) is a type of number
  hs_security_certscore_expired = null
  # hs_security_certscore_gt30d - (optional) is a type of number
  hs_security_certscore_gt30d = null
  # hs_security_certscore_le07d - (optional) is a type of number
  hs_security_certscore_le07d = null
  # hs_security_certscore_le30d - (optional) is a type of number
  hs_security_certscore_le30d = null
  # hs_security_chain_invalidity_penalty - (optional) is a type of number
  hs_security_chain_invalidity_penalty = null
  # hs_security_cipherscore_eq000b - (optional) is a type of number
  hs_security_cipherscore_eq000b = null
  # hs_security_cipherscore_ge128b - (optional) is a type of number
  hs_security_cipherscore_ge128b = null
  # hs_security_cipherscore_lt128b - (optional) is a type of number
  hs_security_cipherscore_lt128b = null
  # hs_security_encalgo_score_none - (optional) is a type of number
  hs_security_encalgo_score_none = null
  # hs_security_encalgo_score_rc4 - (optional) is a type of number
  hs_security_encalgo_score_rc4 = null
  # hs_security_hsts_penalty - (optional) is a type of number
  hs_security_hsts_penalty = null
  # hs_security_nonpfs_penalty - (optional) is a type of number
  hs_security_nonpfs_penalty = null
  # hs_security_selfsignedcert_penalty - (optional) is a type of number
  hs_security_selfsignedcert_penalty = null
  # hs_security_ssl30_score - (optional) is a type of number
  hs_security_ssl30_score = null
  # hs_security_tls10_score - (optional) is a type of number
  hs_security_tls10_score = null
  # hs_security_tls11_score - (optional) is a type of number
  hs_security_tls11_score = null
  # hs_security_tls12_score - (optional) is a type of number
  hs_security_tls12_score = null
  # hs_security_weak_signature_algo_penalty - (optional) is a type of number
  hs_security_weak_signature_algo_penalty = null
  # name - (required) is a type of string
  name = null
  # ondemand_metrics_idle_timeout - (optional) is a type of number
  ondemand_metrics_idle_timeout = null
  # resp_code_block - (optional) is a type of list of string
  resp_code_block = []
  # sip_log_depth - (optional) is a type of number
  sip_log_depth = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null

  client_log_config = [{
    enable_significant_log_collection = null
    filtered_log_processing           = null
    non_significant_log_processing    = null
    significant_log_processing        = null
  }]

  client_log_streaming_config = [{
    external_server      = null
    external_server_port = null
    format_config = [{
      format          = null
      included_fields = []
    }]
    log_types_to_send   = null
    max_logs_per_second = null
    protocol            = null
    syslog_config = [{
      facility                     = null
      filtered_log_severity        = null
      hostname                     = null
      non_significant_log_severity = null
      significant_log_severity     = null
    }]
  }]

  ranges = [{
    begin = null
    end   = null
  }]

  sensitive_log_profile = [{
    header_field_rules = [{
      action  = null
      enabled = null
      index   = null
      match = [{
        match_criteria    = null
        match_str         = []
        string_group_refs = []
      }]
      name = null
    }]
    waf_field_rules = [{
      action  = null
      enabled = null
      index   = null
      match = [{
        match_criteria    = null
        match_str         = []
        string_group_refs = []
      }]
      name = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "apdex_response_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "apdex_response_tolerated_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "apdex_rtt_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "apdex_rtt_tolerated_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "apdex_rum_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "apdex_rum_tolerated_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "apdex_server_response_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "apdex_server_response_tolerated_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "apdex_server_rtt_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "apdex_server_rtt_tolerated_factor" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_lossy_ooo_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_lossy_timeo_rexmt_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_lossy_total_rexmt_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_lossy_zero_win_size_event_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_server_lossy_ooo_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_server_lossy_timeo_rexmt_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_server_lossy_total_rexmt_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_server_lossy_zero_win_size_event_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_ondemand_metrics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disable_se_analytics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disable_server_analytics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "disable_vs_analytics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_advanced_analytics" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_client_close_before_request_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_dns_policy_drop_as_significant" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_gs_down_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_http_error_codes" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "exclude_invalid_dns_domain_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_invalid_dns_query_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_no_dns_record_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_no_valid_gs_member_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_persistence_change_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_server_dns_error_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_server_tcp_reset_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_sip_error_codes" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "exclude_syn_retransmit_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_tcp_reset_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "exclude_unsupported_dns_query_as_error" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "healthscore_max_server_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_event_throttle_window" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_max_anomaly_penalty" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_max_resources_penalty" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_max_security_penalty" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_min_dos_rate" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_performance_boost" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_pscore_traffic_threshold_l4_client" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_pscore_traffic_threshold_l4_server" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_certscore_expired" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_certscore_gt30d" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_certscore_le07d" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_certscore_le30d" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_chain_invalidity_penalty" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_cipherscore_eq000b" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_cipherscore_ge128b" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_cipherscore_lt128b" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_encalgo_score_none" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_encalgo_score_rc4" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_hsts_penalty" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_nonpfs_penalty" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_selfsignedcert_penalty" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_ssl30_score" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_tls10_score" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_tls11_score" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_tls12_score" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "hs_security_weak_signature_algo_penalty" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "ondemand_metrics_idle_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resp_code_block" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "sip_log_depth" {
  description = "(optional)"
  type        = number
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

variable "client_log_config" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      enable_significant_log_collection = bool
      filtered_log_processing           = string
      non_significant_log_processing    = string
      significant_log_processing        = string
    }
  ))
  default = []
}

variable "client_log_streaming_config" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      external_server      = string
      external_server_port = number
      format_config = set(object(
        {
          format          = string
          included_fields = list(string)
        }
      ))
      log_types_to_send   = string
      max_logs_per_second = number
      protocol            = string
      syslog_config = set(object(
        {
          facility                     = number
          filtered_log_severity        = number
          hostname                     = string
          non_significant_log_severity = number
          significant_log_severity     = number
        }
      ))
    }
  ))
  default = []
}

variable "ranges" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      begin = number
      end   = number
    }
  ))
  default = []
}

variable "sensitive_log_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      header_field_rules = list(object(
        {
          action  = string
          enabled = bool
          index   = number
          match = set(object(
            {
              match_criteria    = string
              match_str         = list(string)
              string_group_refs = list(string)
            }
          ))
          name = string
        }
      ))
      waf_field_rules = list(object(
        {
          action  = string
          enabled = bool
          index   = number
          match = set(object(
            {
              match_criteria    = string
              match_str         = list(string)
              string_group_refs = list(string)
            }
          ))
          name = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_analyticsprofile" "this" {
  apdex_response_threshold                        = var.apdex_response_threshold
  apdex_response_tolerated_factor                 = var.apdex_response_tolerated_factor
  apdex_rtt_threshold                             = var.apdex_rtt_threshold
  apdex_rtt_tolerated_factor                      = var.apdex_rtt_tolerated_factor
  apdex_rum_threshold                             = var.apdex_rum_threshold
  apdex_rum_tolerated_factor                      = var.apdex_rum_tolerated_factor
  apdex_server_response_threshold                 = var.apdex_server_response_threshold
  apdex_server_response_tolerated_factor          = var.apdex_server_response_tolerated_factor
  apdex_server_rtt_threshold                      = var.apdex_server_rtt_threshold
  apdex_server_rtt_tolerated_factor               = var.apdex_server_rtt_tolerated_factor
  conn_lossy_ooo_threshold                        = var.conn_lossy_ooo_threshold
  conn_lossy_timeo_rexmt_threshold                = var.conn_lossy_timeo_rexmt_threshold
  conn_lossy_total_rexmt_threshold                = var.conn_lossy_total_rexmt_threshold
  conn_lossy_zero_win_size_event_threshold        = var.conn_lossy_zero_win_size_event_threshold
  conn_server_lossy_ooo_threshold                 = var.conn_server_lossy_ooo_threshold
  conn_server_lossy_timeo_rexmt_threshold         = var.conn_server_lossy_timeo_rexmt_threshold
  conn_server_lossy_total_rexmt_threshold         = var.conn_server_lossy_total_rexmt_threshold
  conn_server_lossy_zero_win_size_event_threshold = var.conn_server_lossy_zero_win_size_event_threshold
  description                                     = var.description
  disable_ondemand_metrics                        = var.disable_ondemand_metrics
  disable_se_analytics                            = var.disable_se_analytics
  disable_server_analytics                        = var.disable_server_analytics
  disable_vs_analytics                            = var.disable_vs_analytics
  enable_advanced_analytics                       = var.enable_advanced_analytics
  exclude_client_close_before_request_as_error    = var.exclude_client_close_before_request_as_error
  exclude_dns_policy_drop_as_significant          = var.exclude_dns_policy_drop_as_significant
  exclude_gs_down_as_error                        = var.exclude_gs_down_as_error
  exclude_http_error_codes                        = var.exclude_http_error_codes
  exclude_invalid_dns_domain_as_error             = var.exclude_invalid_dns_domain_as_error
  exclude_invalid_dns_query_as_error              = var.exclude_invalid_dns_query_as_error
  exclude_no_dns_record_as_error                  = var.exclude_no_dns_record_as_error
  exclude_no_valid_gs_member_as_error             = var.exclude_no_valid_gs_member_as_error
  exclude_persistence_change_as_error             = var.exclude_persistence_change_as_error
  exclude_server_dns_error_as_error               = var.exclude_server_dns_error_as_error
  exclude_server_tcp_reset_as_error               = var.exclude_server_tcp_reset_as_error
  exclude_sip_error_codes                         = var.exclude_sip_error_codes
  exclude_syn_retransmit_as_error                 = var.exclude_syn_retransmit_as_error
  exclude_tcp_reset_as_error                      = var.exclude_tcp_reset_as_error
  exclude_unsupported_dns_query_as_error          = var.exclude_unsupported_dns_query_as_error
  healthscore_max_server_limit                    = var.healthscore_max_server_limit
  hs_event_throttle_window                        = var.hs_event_throttle_window
  hs_max_anomaly_penalty                          = var.hs_max_anomaly_penalty
  hs_max_resources_penalty                        = var.hs_max_resources_penalty
  hs_max_security_penalty                         = var.hs_max_security_penalty
  hs_min_dos_rate                                 = var.hs_min_dos_rate
  hs_performance_boost                            = var.hs_performance_boost
  hs_pscore_traffic_threshold_l4_client           = var.hs_pscore_traffic_threshold_l4_client
  hs_pscore_traffic_threshold_l4_server           = var.hs_pscore_traffic_threshold_l4_server
  hs_security_certscore_expired                   = var.hs_security_certscore_expired
  hs_security_certscore_gt30d                     = var.hs_security_certscore_gt30d
  hs_security_certscore_le07d                     = var.hs_security_certscore_le07d
  hs_security_certscore_le30d                     = var.hs_security_certscore_le30d
  hs_security_chain_invalidity_penalty            = var.hs_security_chain_invalidity_penalty
  hs_security_cipherscore_eq000b                  = var.hs_security_cipherscore_eq000b
  hs_security_cipherscore_ge128b                  = var.hs_security_cipherscore_ge128b
  hs_security_cipherscore_lt128b                  = var.hs_security_cipherscore_lt128b
  hs_security_encalgo_score_none                  = var.hs_security_encalgo_score_none
  hs_security_encalgo_score_rc4                   = var.hs_security_encalgo_score_rc4
  hs_security_hsts_penalty                        = var.hs_security_hsts_penalty
  hs_security_nonpfs_penalty                      = var.hs_security_nonpfs_penalty
  hs_security_selfsignedcert_penalty              = var.hs_security_selfsignedcert_penalty
  hs_security_ssl30_score                         = var.hs_security_ssl30_score
  hs_security_tls10_score                         = var.hs_security_tls10_score
  hs_security_tls11_score                         = var.hs_security_tls11_score
  hs_security_tls12_score                         = var.hs_security_tls12_score
  hs_security_weak_signature_algo_penalty         = var.hs_security_weak_signature_algo_penalty
  name                                            = var.name
  ondemand_metrics_idle_timeout                   = var.ondemand_metrics_idle_timeout
  resp_code_block                                 = var.resp_code_block
  sip_log_depth                                   = var.sip_log_depth
  tenant_ref                                      = var.tenant_ref
  uuid                                            = var.uuid

  dynamic "client_log_config" {
    for_each = var.client_log_config
    content {
      enable_significant_log_collection = client_log_config.value["enable_significant_log_collection"]
      filtered_log_processing           = client_log_config.value["filtered_log_processing"]
      non_significant_log_processing    = client_log_config.value["non_significant_log_processing"]
      significant_log_processing        = client_log_config.value["significant_log_processing"]
    }
  }

  dynamic "client_log_streaming_config" {
    for_each = var.client_log_streaming_config
    content {
      external_server      = client_log_streaming_config.value["external_server"]
      external_server_port = client_log_streaming_config.value["external_server_port"]
      log_types_to_send    = client_log_streaming_config.value["log_types_to_send"]
      max_logs_per_second  = client_log_streaming_config.value["max_logs_per_second"]
      protocol             = client_log_streaming_config.value["protocol"]

      dynamic "format_config" {
        for_each = client_log_streaming_config.value.format_config
        content {
          format          = format_config.value["format"]
          included_fields = format_config.value["included_fields"]
        }
      }

      dynamic "syslog_config" {
        for_each = client_log_streaming_config.value.syslog_config
        content {
          facility                     = syslog_config.value["facility"]
          filtered_log_severity        = syslog_config.value["filtered_log_severity"]
          hostname                     = syslog_config.value["hostname"]
          non_significant_log_severity = syslog_config.value["non_significant_log_severity"]
          significant_log_severity     = syslog_config.value["significant_log_severity"]
        }
      }

    }
  }

  dynamic "ranges" {
    for_each = var.ranges
    content {
      begin = ranges.value["begin"]
      end   = ranges.value["end"]
    }
  }

  dynamic "sensitive_log_profile" {
    for_each = var.sensitive_log_profile
    content {

      dynamic "header_field_rules" {
        for_each = sensitive_log_profile.value.header_field_rules
        content {
          action  = header_field_rules.value["action"]
          enabled = header_field_rules.value["enabled"]
          index   = header_field_rules.value["index"]
          name    = header_field_rules.value["name"]

          dynamic "match" {
            for_each = header_field_rules.value.match
            content {
              match_criteria    = match.value["match_criteria"]
              match_str         = match.value["match_str"]
              string_group_refs = match.value["string_group_refs"]
            }
          }

        }
      }

      dynamic "waf_field_rules" {
        for_each = sensitive_log_profile.value.waf_field_rules
        content {
          action  = waf_field_rules.value["action"]
          enabled = waf_field_rules.value["enabled"]
          index   = waf_field_rules.value["index"]
          name    = waf_field_rules.value["name"]

          dynamic "match" {
            for_each = waf_field_rules.value.match
            content {
              match_criteria    = match.value["match_criteria"]
              match_str         = match.value["match_str"]
              string_group_refs = match.value["string_group_refs"]
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
output "description" {
  description = "returns a string"
  value       = avi_analyticsprofile.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_analyticsprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_analyticsprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_analyticsprofile.this.uuid
}

output "this" {
  value = avi_analyticsprofile.this
}
```

[top](#index)