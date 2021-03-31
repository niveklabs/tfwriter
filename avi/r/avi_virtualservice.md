# avi_virtualservice

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
module "avi_virtualservice" {
  source = "./modules/avi/r/avi_virtualservice"

  # active_standby_se_tag - (optional) is a type of string
  active_standby_se_tag = null
  # allow_invalid_client_cert - (optional) is a type of bool
  allow_invalid_client_cert = null
  # analytics_profile_ref - (optional) is a type of string
  analytics_profile_ref = null
  # apic_contract_graph - (optional) is a type of string
  apic_contract_graph = null
  # application_profile_ref - (optional) is a type of string
  application_profile_ref = null
  # bulk_sync_kvcache - (optional) is a type of bool
  bulk_sync_kvcache = null
  # close_client_conn_on_config_update - (optional) is a type of bool
  close_client_conn_on_config_update = null
  # cloud_config_cksum - (optional) is a type of string
  cloud_config_cksum = null
  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # cloud_type - (optional) is a type of string
  cloud_type = null
  # created_by - (optional) is a type of string
  created_by = null
  # delay_fairness - (optional) is a type of bool
  delay_fairness = null
  # description - (optional) is a type of string
  description = null
  # east_west_placement - (optional) is a type of bool
  east_west_placement = null
  # enable_autogw - (optional) is a type of bool
  enable_autogw = null
  # enable_rhi - (optional) is a type of bool
  enable_rhi = null
  # enable_rhi_snat - (optional) is a type of bool
  enable_rhi_snat = null
  # enabled - (optional) is a type of bool
  enabled = null
  # error_page_profile_ref - (optional) is a type of string
  error_page_profile_ref = null
  # flow_dist - (optional) is a type of string
  flow_dist = null
  # flow_label_type - (optional) is a type of string
  flow_label_type = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # host_name_xlate - (optional) is a type of string
  host_name_xlate = null
  # ign_pool_net_reach - (optional) is a type of bool
  ign_pool_net_reach = null
  # limit_doser - (optional) is a type of bool
  limit_doser = null
  # max_cps_per_client - (optional) is a type of number
  max_cps_per_client = null
  # microservice_ref - (optional) is a type of string
  microservice_ref = null
  # min_pools_up - (optional) is a type of number
  min_pools_up = null
  # name - (required) is a type of string
  name = null
  # network_profile_ref - (optional) is a type of string
  network_profile_ref = null
  # network_security_policy_ref - (optional) is a type of string
  network_security_policy_ref = null
  # nsx_securitygroup - (optional) is a type of list of string
  nsx_securitygroup = []
  # pool_group_ref - (optional) is a type of string
  pool_group_ref = null
  # pool_ref - (optional) is a type of string
  pool_ref = null
  # remove_listening_port_on_vs_down - (optional) is a type of bool
  remove_listening_port_on_vs_down = null
  # scaleout_ecmp - (optional) is a type of bool
  scaleout_ecmp = null
  # se_group_ref - (optional) is a type of string
  se_group_ref = null
  # security_policy_ref - (optional) is a type of string
  security_policy_ref = null
  # server_network_profile_ref - (optional) is a type of string
  server_network_profile_ref = null
  # service_metadata - (optional) is a type of string
  service_metadata = null
  # ssl_key_and_certificate_refs - (optional) is a type of list of string
  ssl_key_and_certificate_refs = []
  # ssl_profile_ref - (optional) is a type of string
  ssl_profile_ref = null
  # ssl_sess_cache_avg_size - (optional) is a type of number
  ssl_sess_cache_avg_size = null
  # sso_policy_ref - (optional) is a type of string
  sso_policy_ref = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # test_se_datastore_level_1_ref - (optional) is a type of string
  test_se_datastore_level_1_ref = null
  # traffic_clone_profile_ref - (optional) is a type of string
  traffic_clone_profile_ref = null
  # traffic_enabled - (optional) is a type of bool
  traffic_enabled = null
  # type - (optional) is a type of string
  type = null
  # use_bridge_ip_as_vip - (optional) is a type of bool
  use_bridge_ip_as_vip = null
  # use_vip_as_snat - (optional) is a type of bool
  use_vip_as_snat = null
  # uuid - (optional) is a type of string
  uuid = null
  # vh_domain_name - (optional) is a type of list of string
  vh_domain_name = []
  # vh_parent_vs_uuid - (optional) is a type of string
  vh_parent_vs_uuid = null
  # vrf_context_ref - (optional) is a type of string
  vrf_context_ref = null
  # vsvip_cloud_config_cksum - (optional) is a type of string
  vsvip_cloud_config_cksum = null
  # vsvip_ref - (optional) is a type of string
  vsvip_ref = null
  # waf_policy_ref - (optional) is a type of string
  waf_policy_ref = null
  # weight - (optional) is a type of number
  weight = null

  analytics_policy = [{
    all_headers     = null
    client_insights = null
    client_insights_sampling = [{
      client_ip = [{
        addrs = [{
          addr = null
          type = null
        }]
        group_refs     = []
        match_criteria = null
        prefixes = [{
          ip_addr = [{
            addr = null
            type = null
          }]
          mask = null
        }]
        ranges = [{
          begin = [{
            addr = null
            type = null
          }]
          end = [{
            addr = null
            type = null
          }]
        }]
      }]
      sample_uris = [{
        match_criteria    = null
        match_str         = []
        string_group_refs = []
      }]
      skip_uris = [{
        match_criteria    = null
        match_str         = []
        string_group_refs = []
      }]
    }]
    client_log_filters = [{
      all_headers = null
      client_ip = [{
        addrs = [{
          addr = null
          type = null
        }]
        group_refs     = []
        match_criteria = null
        prefixes = [{
          ip_addr = [{
            addr = null
            type = null
          }]
          mask = null
        }]
        ranges = [{
          begin = [{
            addr = null
            type = null
          }]
          end = [{
            addr = null
            type = null
          }]
        }]
      }]
      duration = null
      enabled  = null
      index    = null
      name     = null
      uri = [{
        match_criteria    = null
        match_str         = []
        string_group_refs = []
      }]
    }]
    full_client_logs = [{
      duration = null
      enabled  = null
      throttle = null
    }]
    metrics_realtime_update = [{
      duration = null
      enabled  = null
    }]
    significant_log_throttle = null
    udf_log_throttle         = null
  }]

  client_auth = [{
    auth_profile_ref = null
    realm            = null
    request_uri_path = [{
      match_criteria    = null
      match_str         = []
      string_group_refs = []
    }]
    type = null
  }]

  connections_rate_limit = [{
    action = [{
      file = [{
        content_type = null
        file_content = null
      }]
      redirect = [{
        host = [{
          tokens = [{
            end_index   = null
            start_index = null
            str_value   = null
            type        = null
          }]
          type = null
        }]
        keep_query = null
        path = [{
          tokens = [{
            end_index   = null
            start_index = null
            str_value   = null
            type        = null
          }]
          type = null
        }]
        port        = null
        protocol    = null
        status_code = null
      }]
      status_code = null
      type        = null
    }]
    explicit_tracking = null
    fine_grain        = null
    http_cookie       = null
    http_header       = null
    rate_limiter = [{
      burst_sz = null
      count    = null
      name     = null
      period   = null
    }]
  }]

  content_rewrite = [{
    req_match_replace_pair = [{
      match_string = null
      replacement_string = [{
        type = null
        val  = null
      }]
    }]
    request_rewrite_enabled  = null
    response_rewrite_enabled = null
    rewritable_content_ref   = null
    rsp_match_replace_pair = [{
      match_string = null
      replacement_string = [{
        type = null
        val  = null
      }]
    }]
  }]

  dns_info = [{
    algorithm = null
    cname = [{
      cname = null
    }]
    fqdn                    = null
    num_records_in_response = null
    ttl                     = null
    type                    = null
  }]

  dns_policies = [{
    dns_policy_ref = null
    index          = null
  }]

  http_policies = [{
    http_policy_set_ref = null
    index               = null
  }]

  l4_policies = [{
    index             = null
    l4_policy_set_ref = null
  }]

  performance_limits = [{
    max_concurrent_connections = null
    max_throughput             = null
  }]

  requests_rate_limit = [{
    action = [{
      file = [{
        content_type = null
        file_content = null
      }]
      redirect = [{
        host = [{
          tokens = [{
            end_index   = null
            start_index = null
            str_value   = null
            type        = null
          }]
          type = null
        }]
        keep_query = null
        path = [{
          tokens = [{
            end_index   = null
            start_index = null
            str_value   = null
            type        = null
          }]
          type = null
        }]
        port        = null
        protocol    = null
        status_code = null
      }]
      status_code = null
      type        = null
    }]
    explicit_tracking = null
    fine_grain        = null
    http_cookie       = null
    http_header       = null
    rate_limiter = [{
      burst_sz = null
      count    = null
      name     = null
      period   = null
    }]
  }]

  saml_sp_config = [{
    cookie_name    = null
    cookie_timeout = null
    entity_id      = null
    key = [{
      aes_key  = null
      hmac_key = null
      name     = null
    }]
    signing_ssl_key_and_certificate_ref = null
    single_signon_url                   = null
  }]

  service_pool_select = [{
    service_pool_group_ref = null
    service_pool_ref       = null
    service_port           = null
    service_port_range_end = null
    service_protocol       = null
  }]

  services = [{
    enable_ssl                       = null
    override_application_profile_ref = null
    override_network_profile_ref     = null
    port                             = null
    port_range_end                   = null
  }]

  sideband_profile = [{
    ip = [{
      addr = null
      type = null
    }]
    sideband_max_request_body_size = null
  }]

  snat_ip = [{
    addr = null
    type = null
  }]

  ssl_profile_selectors = [{
    client_ip_list = [{
      addrs = [{
        addr = null
        type = null
      }]
      group_refs     = []
      match_criteria = null
      prefixes = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      ranges = [{
        begin = [{
          addr = null
          type = null
        }]
        end = [{
          addr = null
          type = null
        }]
      }]
    }]
    ssl_profile_ref = null
  }]

  static_dns_records = [{
    algorithm = null
    cname = [{
      cname = null
    }]
    delegated   = null
    description = null
    fqdn        = []
    ip6_address = [{
      ip6_address = [{
        addr = null
        type = null
      }]
    }]
    ip_address = [{
      ip_address = [{
        addr = null
        type = null
      }]
    }]
    metadata = null
    mx_records = [{
      host     = null
      priority = null
    }]
    ns = [{
      ip6_address = [{
        addr = null
        type = null
      }]
      ip_address = [{
        addr = null
        type = null
      }]
      nsname = null
    }]
    num_records_in_response = null
    service_locator = [{
      port     = null
      priority = null
      target   = null
      weight   = null
    }]
    ttl = null
    txt_records = [{
      text_str = null
    }]
    type           = null
    wildcard_match = null
  }]

  topology_policies = [{
    dns_policy_ref = null
    index          = null
  }]

  vip = [{
    auto_allocate_floating_ip = null
    auto_allocate_ip          = null
    auto_allocate_ip_type     = null
    availability_zone         = null
    avi_allocated_fip         = null
    avi_allocated_vip         = null
    discovered_networks = [{
      network_ref = null
      subnet = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      subnet6 = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
    }]
    enabled = null
    floating_ip = [{
      addr = null
      type = null
    }]
    floating_ip6 = [{
      addr = null
      type = null
    }]
    floating_subnet6_uuid = null
    floating_subnet_uuid  = null
    ip6_address = [{
      addr = null
      type = null
    }]
    ip_address = [{
      addr = null
      type = null
    }]
    ipam_network_subnet = [{
      network_ref = null
      subnet = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      subnet6 = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      subnet6_uuid = null
      subnet_uuid  = null
    }]
    network_ref = null
    placement_networks = [{
      network_ref = null
      subnet = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
      subnet6 = [{
        ip_addr = [{
          addr = null
          type = null
        }]
        mask = null
      }]
    }]
    port_uuid = null
    subnet = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    subnet6 = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
    subnet6_uuid = null
    subnet_uuid  = null
    vip_id       = null
  }]

  vs_datascripts = [{
    index                 = null
    vs_datascript_set_ref = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "active_standby_se_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allow_invalid_client_cert" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "analytics_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "apic_contract_graph" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bulk_sync_kvcache" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "close_client_conn_on_config_update" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cloud_config_cksum" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delay_fairness" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "east_west_placement" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_autogw" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_rhi" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_rhi_snat" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "error_page_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flow_dist" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flow_label_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_name_xlate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ign_pool_net_reach" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "limit_doser" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_cps_per_client" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "microservice_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "min_pools_up" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_security_policy_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "nsx_securitygroup" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "pool_group_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pool_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "remove_listening_port_on_vs_down" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "scaleout_ecmp" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "se_group_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_policy_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_network_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_key_and_certificate_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "ssl_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_sess_cache_avg_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "sso_policy_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "test_se_datastore_level_1_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_clone_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "traffic_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_bridge_ip_as_vip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "use_vip_as_snat" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vh_domain_name" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "vh_parent_vs_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrf_context_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vsvip_cloud_config_cksum" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vsvip_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "waf_policy_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "analytics_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      all_headers     = bool
      client_insights = string
      client_insights_sampling = set(object(
        {
          client_ip = set(object(
            {
              addrs = list(object(
                {
                  addr = string
                  type = string
                }
              ))
              group_refs     = list(string)
              match_criteria = string
              prefixes = list(object(
                {
                  ip_addr = set(object(
                    {
                      addr = string
                      type = string
                    }
                  ))
                  mask = number
                }
              ))
              ranges = list(object(
                {
                  begin = set(object(
                    {
                      addr = string
                      type = string
                    }
                  ))
                  end = set(object(
                    {
                      addr = string
                      type = string
                    }
                  ))
                }
              ))
            }
          ))
          sample_uris = set(object(
            {
              match_criteria    = string
              match_str         = list(string)
              string_group_refs = list(string)
            }
          ))
          skip_uris = set(object(
            {
              match_criteria    = string
              match_str         = list(string)
              string_group_refs = list(string)
            }
          ))
        }
      ))
      client_log_filters = list(object(
        {
          all_headers = bool
          client_ip = set(object(
            {
              addrs = list(object(
                {
                  addr = string
                  type = string
                }
              ))
              group_refs     = list(string)
              match_criteria = string
              prefixes = list(object(
                {
                  ip_addr = set(object(
                    {
                      addr = string
                      type = string
                    }
                  ))
                  mask = number
                }
              ))
              ranges = list(object(
                {
                  begin = set(object(
                    {
                      addr = string
                      type = string
                    }
                  ))
                  end = set(object(
                    {
                      addr = string
                      type = string
                    }
                  ))
                }
              ))
            }
          ))
          duration = number
          enabled  = bool
          index    = number
          name     = string
          uri = set(object(
            {
              match_criteria    = string
              match_str         = list(string)
              string_group_refs = list(string)
            }
          ))
        }
      ))
      full_client_logs = set(object(
        {
          duration = number
          enabled  = bool
          throttle = number
        }
      ))
      metrics_realtime_update = set(object(
        {
          duration = number
          enabled  = bool
        }
      ))
      significant_log_throttle = number
      udf_log_throttle         = number
    }
  ))
  default = []
}

variable "client_auth" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      auth_profile_ref = string
      realm            = string
      request_uri_path = set(object(
        {
          match_criteria    = string
          match_str         = list(string)
          string_group_refs = list(string)
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "connections_rate_limit" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action = set(object(
        {
          file = set(object(
            {
              content_type = string
              file_content = string
            }
          ))
          redirect = set(object(
            {
              host = set(object(
                {
                  tokens = list(object(
                    {
                      end_index   = number
                      start_index = number
                      str_value   = string
                      type        = string
                    }
                  ))
                  type = string
                }
              ))
              keep_query = bool
              path = set(object(
                {
                  tokens = list(object(
                    {
                      end_index   = number
                      start_index = number
                      str_value   = string
                      type        = string
                    }
                  ))
                  type = string
                }
              ))
              port        = number
              protocol    = string
              status_code = string
            }
          ))
          status_code = string
          type        = string
        }
      ))
      explicit_tracking = bool
      fine_grain        = bool
      http_cookie       = string
      http_header       = string
      rate_limiter = set(object(
        {
          burst_sz = number
          count    = number
          name     = string
          period   = number
        }
      ))
    }
  ))
  default = []
}

variable "content_rewrite" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      req_match_replace_pair = list(object(
        {
          match_string = string
          replacement_string = set(object(
            {
              type = string
              val  = string
            }
          ))
        }
      ))
      request_rewrite_enabled  = bool
      response_rewrite_enabled = bool
      rewritable_content_ref   = string
      rsp_match_replace_pair = list(object(
        {
          match_string = string
          replacement_string = set(object(
            {
              type = string
              val  = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "dns_info" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      algorithm = string
      cname = set(object(
        {
          cname = string
        }
      ))
      fqdn                    = string
      num_records_in_response = number
      ttl                     = number
      type                    = string
    }
  ))
  default = []
}

variable "dns_policies" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dns_policy_ref = string
      index          = number
    }
  ))
  default = []
}

variable "http_policies" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      http_policy_set_ref = string
      index               = number
    }
  ))
  default = []
}

variable "l4_policies" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      index             = number
      l4_policy_set_ref = string
    }
  ))
  default = []
}

variable "performance_limits" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      max_concurrent_connections = number
      max_throughput             = number
    }
  ))
  default = []
}

variable "requests_rate_limit" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action = set(object(
        {
          file = set(object(
            {
              content_type = string
              file_content = string
            }
          ))
          redirect = set(object(
            {
              host = set(object(
                {
                  tokens = list(object(
                    {
                      end_index   = number
                      start_index = number
                      str_value   = string
                      type        = string
                    }
                  ))
                  type = string
                }
              ))
              keep_query = bool
              path = set(object(
                {
                  tokens = list(object(
                    {
                      end_index   = number
                      start_index = number
                      str_value   = string
                      type        = string
                    }
                  ))
                  type = string
                }
              ))
              port        = number
              protocol    = string
              status_code = string
            }
          ))
          status_code = string
          type        = string
        }
      ))
      explicit_tracking = bool
      fine_grain        = bool
      http_cookie       = string
      http_header       = string
      rate_limiter = set(object(
        {
          burst_sz = number
          count    = number
          name     = string
          period   = number
        }
      ))
    }
  ))
  default = []
}

variable "saml_sp_config" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cookie_name    = string
      cookie_timeout = number
      entity_id      = string
      key = list(object(
        {
          aes_key  = string
          hmac_key = string
          name     = string
        }
      ))
      signing_ssl_key_and_certificate_ref = string
      single_signon_url                   = string
    }
  ))
  default = []
}

variable "service_pool_select" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      service_pool_group_ref = string
      service_pool_ref       = string
      service_port           = number
      service_port_range_end = number
      service_protocol       = string
    }
  ))
  default = []
}

variable "services" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      enable_ssl                       = bool
      override_application_profile_ref = string
      override_network_profile_ref     = string
      port                             = number
      port_range_end                   = number
    }
  ))
  default = []
}

variable "sideband_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      ip = list(object(
        {
          addr = string
          type = string
        }
      ))
      sideband_max_request_body_size = number
    }
  ))
  default = []
}

variable "snat_ip" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      addr = string
      type = string
    }
  ))
  default = []
}

variable "ssl_profile_selectors" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      client_ip_list = set(object(
        {
          addrs = list(object(
            {
              addr = string
              type = string
            }
          ))
          group_refs     = list(string)
          match_criteria = string
          prefixes = list(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          ranges = list(object(
            {
              begin = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              end = set(object(
                {
                  addr = string
                  type = string
                }
              ))
            }
          ))
        }
      ))
      ssl_profile_ref = string
    }
  ))
  default = []
}

variable "static_dns_records" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      algorithm = string
      cname = set(object(
        {
          cname = string
        }
      ))
      delegated   = bool
      description = string
      fqdn        = list(string)
      ip6_address = list(object(
        {
          ip6_address = set(object(
            {
              addr = string
              type = string
            }
          ))
        }
      ))
      ip_address = list(object(
        {
          ip_address = set(object(
            {
              addr = string
              type = string
            }
          ))
        }
      ))
      metadata = string
      mx_records = list(object(
        {
          host     = string
          priority = number
        }
      ))
      ns = list(object(
        {
          ip6_address = set(object(
            {
              addr = string
              type = string
            }
          ))
          ip_address = set(object(
            {
              addr = string
              type = string
            }
          ))
          nsname = string
        }
      ))
      num_records_in_response = number
      service_locator = list(object(
        {
          port     = number
          priority = number
          target   = string
          weight   = number
        }
      ))
      ttl = number
      txt_records = list(object(
        {
          text_str = string
        }
      ))
      type           = string
      wildcard_match = bool
    }
  ))
  default = []
}

variable "topology_policies" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      dns_policy_ref = string
      index          = number
    }
  ))
  default = []
}

variable "vip" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auto_allocate_floating_ip = bool
      auto_allocate_ip          = bool
      auto_allocate_ip_type     = string
      availability_zone         = string
      avi_allocated_fip         = bool
      avi_allocated_vip         = bool
      discovered_networks = list(object(
        {
          network_ref = string
          subnet = list(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          subnet6 = list(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
        }
      ))
      enabled = bool
      floating_ip = set(object(
        {
          addr = string
          type = string
        }
      ))
      floating_ip6 = set(object(
        {
          addr = string
          type = string
        }
      ))
      floating_subnet6_uuid = string
      floating_subnet_uuid  = string
      ip6_address = set(object(
        {
          addr = string
          type = string
        }
      ))
      ip_address = set(object(
        {
          addr = string
          type = string
        }
      ))
      ipam_network_subnet = set(object(
        {
          network_ref = string
          subnet = set(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          subnet6 = set(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          subnet6_uuid = string
          subnet_uuid  = string
        }
      ))
      network_ref = string
      placement_networks = list(object(
        {
          network_ref = string
          subnet = set(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
          subnet6 = set(object(
            {
              ip_addr = set(object(
                {
                  addr = string
                  type = string
                }
              ))
              mask = number
            }
          ))
        }
      ))
      port_uuid = string
      subnet = set(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
      subnet6 = set(object(
        {
          ip_addr = set(object(
            {
              addr = string
              type = string
            }
          ))
          mask = number
        }
      ))
      subnet6_uuid = string
      subnet_uuid  = string
      vip_id       = string
    }
  ))
  default = []
}

variable "vs_datascripts" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      index                 = number
      vs_datascript_set_ref = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_virtualservice" "this" {
  active_standby_se_tag              = var.active_standby_se_tag
  allow_invalid_client_cert          = var.allow_invalid_client_cert
  analytics_profile_ref              = var.analytics_profile_ref
  apic_contract_graph                = var.apic_contract_graph
  application_profile_ref            = var.application_profile_ref
  bulk_sync_kvcache                  = var.bulk_sync_kvcache
  close_client_conn_on_config_update = var.close_client_conn_on_config_update
  cloud_config_cksum                 = var.cloud_config_cksum
  cloud_ref                          = var.cloud_ref
  cloud_type                         = var.cloud_type
  created_by                         = var.created_by
  delay_fairness                     = var.delay_fairness
  description                        = var.description
  east_west_placement                = var.east_west_placement
  enable_autogw                      = var.enable_autogw
  enable_rhi                         = var.enable_rhi
  enable_rhi_snat                    = var.enable_rhi_snat
  enabled                            = var.enabled
  error_page_profile_ref             = var.error_page_profile_ref
  flow_dist                          = var.flow_dist
  flow_label_type                    = var.flow_label_type
  fqdn                               = var.fqdn
  host_name_xlate                    = var.host_name_xlate
  ign_pool_net_reach                 = var.ign_pool_net_reach
  limit_doser                        = var.limit_doser
  max_cps_per_client                 = var.max_cps_per_client
  microservice_ref                   = var.microservice_ref
  min_pools_up                       = var.min_pools_up
  name                               = var.name
  network_profile_ref                = var.network_profile_ref
  network_security_policy_ref        = var.network_security_policy_ref
  nsx_securitygroup                  = var.nsx_securitygroup
  pool_group_ref                     = var.pool_group_ref
  pool_ref                           = var.pool_ref
  remove_listening_port_on_vs_down   = var.remove_listening_port_on_vs_down
  scaleout_ecmp                      = var.scaleout_ecmp
  se_group_ref                       = var.se_group_ref
  security_policy_ref                = var.security_policy_ref
  server_network_profile_ref         = var.server_network_profile_ref
  service_metadata                   = var.service_metadata
  ssl_key_and_certificate_refs       = var.ssl_key_and_certificate_refs
  ssl_profile_ref                    = var.ssl_profile_ref
  ssl_sess_cache_avg_size            = var.ssl_sess_cache_avg_size
  sso_policy_ref                     = var.sso_policy_ref
  tenant_ref                         = var.tenant_ref
  test_se_datastore_level_1_ref      = var.test_se_datastore_level_1_ref
  traffic_clone_profile_ref          = var.traffic_clone_profile_ref
  traffic_enabled                    = var.traffic_enabled
  type                               = var.type
  use_bridge_ip_as_vip               = var.use_bridge_ip_as_vip
  use_vip_as_snat                    = var.use_vip_as_snat
  uuid                               = var.uuid
  vh_domain_name                     = var.vh_domain_name
  vh_parent_vs_uuid                  = var.vh_parent_vs_uuid
  vrf_context_ref                    = var.vrf_context_ref
  vsvip_cloud_config_cksum           = var.vsvip_cloud_config_cksum
  vsvip_ref                          = var.vsvip_ref
  waf_policy_ref                     = var.waf_policy_ref
  weight                             = var.weight

  dynamic "analytics_policy" {
    for_each = var.analytics_policy
    content {
      all_headers              = analytics_policy.value["all_headers"]
      client_insights          = analytics_policy.value["client_insights"]
      significant_log_throttle = analytics_policy.value["significant_log_throttle"]
      udf_log_throttle         = analytics_policy.value["udf_log_throttle"]

      dynamic "client_insights_sampling" {
        for_each = analytics_policy.value.client_insights_sampling
        content {

          dynamic "client_ip" {
            for_each = client_insights_sampling.value.client_ip
            content {
              group_refs     = client_ip.value["group_refs"]
              match_criteria = client_ip.value["match_criteria"]

              dynamic "addrs" {
                for_each = client_ip.value.addrs
                content {
                  addr = addrs.value["addr"]
                  type = addrs.value["type"]
                }
              }

              dynamic "prefixes" {
                for_each = client_ip.value.prefixes
                content {
                  mask = prefixes.value["mask"]

                  dynamic "ip_addr" {
                    for_each = prefixes.value.ip_addr
                    content {
                      addr = ip_addr.value["addr"]
                      type = ip_addr.value["type"]
                    }
                  }

                }
              }

              dynamic "ranges" {
                for_each = client_ip.value.ranges
                content {

                  dynamic "begin" {
                    for_each = ranges.value.begin
                    content {
                      addr = begin.value["addr"]
                      type = begin.value["type"]
                    }
                  }

                  dynamic "end" {
                    for_each = ranges.value.end
                    content {
                      addr = end.value["addr"]
                      type = end.value["type"]
                    }
                  }

                }
              }

            }
          }

          dynamic "sample_uris" {
            for_each = client_insights_sampling.value.sample_uris
            content {
              match_criteria    = sample_uris.value["match_criteria"]
              match_str         = sample_uris.value["match_str"]
              string_group_refs = sample_uris.value["string_group_refs"]
            }
          }

          dynamic "skip_uris" {
            for_each = client_insights_sampling.value.skip_uris
            content {
              match_criteria    = skip_uris.value["match_criteria"]
              match_str         = skip_uris.value["match_str"]
              string_group_refs = skip_uris.value["string_group_refs"]
            }
          }

        }
      }

      dynamic "client_log_filters" {
        for_each = analytics_policy.value.client_log_filters
        content {
          all_headers = client_log_filters.value["all_headers"]
          duration    = client_log_filters.value["duration"]
          enabled     = client_log_filters.value["enabled"]
          index       = client_log_filters.value["index"]
          name        = client_log_filters.value["name"]

          dynamic "client_ip" {
            for_each = client_log_filters.value.client_ip
            content {
              group_refs     = client_ip.value["group_refs"]
              match_criteria = client_ip.value["match_criteria"]

              dynamic "addrs" {
                for_each = client_ip.value.addrs
                content {
                  addr = addrs.value["addr"]
                  type = addrs.value["type"]
                }
              }

              dynamic "prefixes" {
                for_each = client_ip.value.prefixes
                content {
                  mask = prefixes.value["mask"]

                  dynamic "ip_addr" {
                    for_each = prefixes.value.ip_addr
                    content {
                      addr = ip_addr.value["addr"]
                      type = ip_addr.value["type"]
                    }
                  }

                }
              }

              dynamic "ranges" {
                for_each = client_ip.value.ranges
                content {

                  dynamic "begin" {
                    for_each = ranges.value.begin
                    content {
                      addr = begin.value["addr"]
                      type = begin.value["type"]
                    }
                  }

                  dynamic "end" {
                    for_each = ranges.value.end
                    content {
                      addr = end.value["addr"]
                      type = end.value["type"]
                    }
                  }

                }
              }

            }
          }

          dynamic "uri" {
            for_each = client_log_filters.value.uri
            content {
              match_criteria    = uri.value["match_criteria"]
              match_str         = uri.value["match_str"]
              string_group_refs = uri.value["string_group_refs"]
            }
          }

        }
      }

      dynamic "full_client_logs" {
        for_each = analytics_policy.value.full_client_logs
        content {
          duration = full_client_logs.value["duration"]
          enabled  = full_client_logs.value["enabled"]
          throttle = full_client_logs.value["throttle"]
        }
      }

      dynamic "metrics_realtime_update" {
        for_each = analytics_policy.value.metrics_realtime_update
        content {
          duration = metrics_realtime_update.value["duration"]
          enabled  = metrics_realtime_update.value["enabled"]
        }
      }

    }
  }

  dynamic "client_auth" {
    for_each = var.client_auth
    content {
      auth_profile_ref = client_auth.value["auth_profile_ref"]
      realm            = client_auth.value["realm"]
      type             = client_auth.value["type"]

      dynamic "request_uri_path" {
        for_each = client_auth.value.request_uri_path
        content {
          match_criteria    = request_uri_path.value["match_criteria"]
          match_str         = request_uri_path.value["match_str"]
          string_group_refs = request_uri_path.value["string_group_refs"]
        }
      }

    }
  }

  dynamic "connections_rate_limit" {
    for_each = var.connections_rate_limit
    content {
      explicit_tracking = connections_rate_limit.value["explicit_tracking"]
      fine_grain        = connections_rate_limit.value["fine_grain"]
      http_cookie       = connections_rate_limit.value["http_cookie"]
      http_header       = connections_rate_limit.value["http_header"]

      dynamic "action" {
        for_each = connections_rate_limit.value.action
        content {
          status_code = action.value["status_code"]
          type        = action.value["type"]

          dynamic "file" {
            for_each = action.value.file
            content {
              content_type = file.value["content_type"]
              file_content = file.value["file_content"]
            }
          }

          dynamic "redirect" {
            for_each = action.value.redirect
            content {
              keep_query  = redirect.value["keep_query"]
              port        = redirect.value["port"]
              protocol    = redirect.value["protocol"]
              status_code = redirect.value["status_code"]

              dynamic "host" {
                for_each = redirect.value.host
                content {
                  type = host.value["type"]

                  dynamic "tokens" {
                    for_each = host.value.tokens
                    content {
                      end_index   = tokens.value["end_index"]
                      start_index = tokens.value["start_index"]
                      str_value   = tokens.value["str_value"]
                      type        = tokens.value["type"]
                    }
                  }

                }
              }

              dynamic "path" {
                for_each = redirect.value.path
                content {
                  type = path.value["type"]

                  dynamic "tokens" {
                    for_each = path.value.tokens
                    content {
                      end_index   = tokens.value["end_index"]
                      start_index = tokens.value["start_index"]
                      str_value   = tokens.value["str_value"]
                      type        = tokens.value["type"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "rate_limiter" {
        for_each = connections_rate_limit.value.rate_limiter
        content {
          burst_sz = rate_limiter.value["burst_sz"]
          count    = rate_limiter.value["count"]
          name     = rate_limiter.value["name"]
          period   = rate_limiter.value["period"]
        }
      }

    }
  }

  dynamic "content_rewrite" {
    for_each = var.content_rewrite
    content {
      request_rewrite_enabled  = content_rewrite.value["request_rewrite_enabled"]
      response_rewrite_enabled = content_rewrite.value["response_rewrite_enabled"]
      rewritable_content_ref   = content_rewrite.value["rewritable_content_ref"]

      dynamic "req_match_replace_pair" {
        for_each = content_rewrite.value.req_match_replace_pair
        content {
          match_string = req_match_replace_pair.value["match_string"]

          dynamic "replacement_string" {
            for_each = req_match_replace_pair.value.replacement_string
            content {
              type = replacement_string.value["type"]
              val  = replacement_string.value["val"]
            }
          }

        }
      }

      dynamic "rsp_match_replace_pair" {
        for_each = content_rewrite.value.rsp_match_replace_pair
        content {
          match_string = rsp_match_replace_pair.value["match_string"]

          dynamic "replacement_string" {
            for_each = rsp_match_replace_pair.value.replacement_string
            content {
              type = replacement_string.value["type"]
              val  = replacement_string.value["val"]
            }
          }

        }
      }

    }
  }

  dynamic "dns_info" {
    for_each = var.dns_info
    content {
      algorithm               = dns_info.value["algorithm"]
      fqdn                    = dns_info.value["fqdn"]
      num_records_in_response = dns_info.value["num_records_in_response"]
      ttl                     = dns_info.value["ttl"]
      type                    = dns_info.value["type"]

      dynamic "cname" {
        for_each = dns_info.value.cname
        content {
          cname = cname.value["cname"]
        }
      }

    }
  }

  dynamic "dns_policies" {
    for_each = var.dns_policies
    content {
      dns_policy_ref = dns_policies.value["dns_policy_ref"]
      index          = dns_policies.value["index"]
    }
  }

  dynamic "http_policies" {
    for_each = var.http_policies
    content {
      http_policy_set_ref = http_policies.value["http_policy_set_ref"]
      index               = http_policies.value["index"]
    }
  }

  dynamic "l4_policies" {
    for_each = var.l4_policies
    content {
      index             = l4_policies.value["index"]
      l4_policy_set_ref = l4_policies.value["l4_policy_set_ref"]
    }
  }

  dynamic "performance_limits" {
    for_each = var.performance_limits
    content {
      max_concurrent_connections = performance_limits.value["max_concurrent_connections"]
      max_throughput             = performance_limits.value["max_throughput"]
    }
  }

  dynamic "requests_rate_limit" {
    for_each = var.requests_rate_limit
    content {
      explicit_tracking = requests_rate_limit.value["explicit_tracking"]
      fine_grain        = requests_rate_limit.value["fine_grain"]
      http_cookie       = requests_rate_limit.value["http_cookie"]
      http_header       = requests_rate_limit.value["http_header"]

      dynamic "action" {
        for_each = requests_rate_limit.value.action
        content {
          status_code = action.value["status_code"]
          type        = action.value["type"]

          dynamic "file" {
            for_each = action.value.file
            content {
              content_type = file.value["content_type"]
              file_content = file.value["file_content"]
            }
          }

          dynamic "redirect" {
            for_each = action.value.redirect
            content {
              keep_query  = redirect.value["keep_query"]
              port        = redirect.value["port"]
              protocol    = redirect.value["protocol"]
              status_code = redirect.value["status_code"]

              dynamic "host" {
                for_each = redirect.value.host
                content {
                  type = host.value["type"]

                  dynamic "tokens" {
                    for_each = host.value.tokens
                    content {
                      end_index   = tokens.value["end_index"]
                      start_index = tokens.value["start_index"]
                      str_value   = tokens.value["str_value"]
                      type        = tokens.value["type"]
                    }
                  }

                }
              }

              dynamic "path" {
                for_each = redirect.value.path
                content {
                  type = path.value["type"]

                  dynamic "tokens" {
                    for_each = path.value.tokens
                    content {
                      end_index   = tokens.value["end_index"]
                      start_index = tokens.value["start_index"]
                      str_value   = tokens.value["str_value"]
                      type        = tokens.value["type"]
                    }
                  }

                }
              }

            }
          }

        }
      }

      dynamic "rate_limiter" {
        for_each = requests_rate_limit.value.rate_limiter
        content {
          burst_sz = rate_limiter.value["burst_sz"]
          count    = rate_limiter.value["count"]
          name     = rate_limiter.value["name"]
          period   = rate_limiter.value["period"]
        }
      }

    }
  }

  dynamic "saml_sp_config" {
    for_each = var.saml_sp_config
    content {
      cookie_name                         = saml_sp_config.value["cookie_name"]
      cookie_timeout                      = saml_sp_config.value["cookie_timeout"]
      entity_id                           = saml_sp_config.value["entity_id"]
      signing_ssl_key_and_certificate_ref = saml_sp_config.value["signing_ssl_key_and_certificate_ref"]
      single_signon_url                   = saml_sp_config.value["single_signon_url"]

      dynamic "key" {
        for_each = saml_sp_config.value.key
        content {
          aes_key  = key.value["aes_key"]
          hmac_key = key.value["hmac_key"]
          name     = key.value["name"]
        }
      }

    }
  }

  dynamic "service_pool_select" {
    for_each = var.service_pool_select
    content {
      service_pool_group_ref = service_pool_select.value["service_pool_group_ref"]
      service_pool_ref       = service_pool_select.value["service_pool_ref"]
      service_port           = service_pool_select.value["service_port"]
      service_port_range_end = service_pool_select.value["service_port_range_end"]
      service_protocol       = service_pool_select.value["service_protocol"]
    }
  }

  dynamic "services" {
    for_each = var.services
    content {
      enable_ssl                       = services.value["enable_ssl"]
      override_application_profile_ref = services.value["override_application_profile_ref"]
      override_network_profile_ref     = services.value["override_network_profile_ref"]
      port                             = services.value["port"]
      port_range_end                   = services.value["port_range_end"]
    }
  }

  dynamic "sideband_profile" {
    for_each = var.sideband_profile
    content {
      sideband_max_request_body_size = sideband_profile.value["sideband_max_request_body_size"]

      dynamic "ip" {
        for_each = sideband_profile.value.ip
        content {
          addr = ip.value["addr"]
          type = ip.value["type"]
        }
      }

    }
  }

  dynamic "snat_ip" {
    for_each = var.snat_ip
    content {
      addr = snat_ip.value["addr"]
      type = snat_ip.value["type"]
    }
  }

  dynamic "ssl_profile_selectors" {
    for_each = var.ssl_profile_selectors
    content {
      ssl_profile_ref = ssl_profile_selectors.value["ssl_profile_ref"]

      dynamic "client_ip_list" {
        for_each = ssl_profile_selectors.value.client_ip_list
        content {
          group_refs     = client_ip_list.value["group_refs"]
          match_criteria = client_ip_list.value["match_criteria"]

          dynamic "addrs" {
            for_each = client_ip_list.value.addrs
            content {
              addr = addrs.value["addr"]
              type = addrs.value["type"]
            }
          }

          dynamic "prefixes" {
            for_each = client_ip_list.value.prefixes
            content {
              mask = prefixes.value["mask"]

              dynamic "ip_addr" {
                for_each = prefixes.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "ranges" {
            for_each = client_ip_list.value.ranges
            content {

              dynamic "begin" {
                for_each = ranges.value.begin
                content {
                  addr = begin.value["addr"]
                  type = begin.value["type"]
                }
              }

              dynamic "end" {
                for_each = ranges.value.end
                content {
                  addr = end.value["addr"]
                  type = end.value["type"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "static_dns_records" {
    for_each = var.static_dns_records
    content {
      algorithm               = static_dns_records.value["algorithm"]
      delegated               = static_dns_records.value["delegated"]
      description             = static_dns_records.value["description"]
      fqdn                    = static_dns_records.value["fqdn"]
      metadata                = static_dns_records.value["metadata"]
      num_records_in_response = static_dns_records.value["num_records_in_response"]
      ttl                     = static_dns_records.value["ttl"]
      type                    = static_dns_records.value["type"]
      wildcard_match          = static_dns_records.value["wildcard_match"]

      dynamic "cname" {
        for_each = static_dns_records.value.cname
        content {
          cname = cname.value["cname"]
        }
      }

      dynamic "ip6_address" {
        for_each = static_dns_records.value.ip6_address
        content {

          dynamic "ip6_address" {
            for_each = ip6_address.value.ip6_address
            content {
              addr = ip6_address.value["addr"]
              type = ip6_address.value["type"]
            }
          }

        }
      }

      dynamic "ip_address" {
        for_each = static_dns_records.value.ip_address
        content {

          dynamic "ip_address" {
            for_each = ip_address.value.ip_address
            content {
              addr = ip_address.value["addr"]
              type = ip_address.value["type"]
            }
          }

        }
      }

      dynamic "mx_records" {
        for_each = static_dns_records.value.mx_records
        content {
          host     = mx_records.value["host"]
          priority = mx_records.value["priority"]
        }
      }

      dynamic "ns" {
        for_each = static_dns_records.value.ns
        content {
          nsname = ns.value["nsname"]

          dynamic "ip6_address" {
            for_each = ns.value.ip6_address
            content {
              addr = ip6_address.value["addr"]
              type = ip6_address.value["type"]
            }
          }

          dynamic "ip_address" {
            for_each = ns.value.ip_address
            content {
              addr = ip_address.value["addr"]
              type = ip_address.value["type"]
            }
          }

        }
      }

      dynamic "service_locator" {
        for_each = static_dns_records.value.service_locator
        content {
          port     = service_locator.value["port"]
          priority = service_locator.value["priority"]
          target   = service_locator.value["target"]
          weight   = service_locator.value["weight"]
        }
      }

      dynamic "txt_records" {
        for_each = static_dns_records.value.txt_records
        content {
          text_str = txt_records.value["text_str"]
        }
      }

    }
  }

  dynamic "topology_policies" {
    for_each = var.topology_policies
    content {
      dns_policy_ref = topology_policies.value["dns_policy_ref"]
      index          = topology_policies.value["index"]
    }
  }

  dynamic "vip" {
    for_each = var.vip
    content {
      auto_allocate_floating_ip = vip.value["auto_allocate_floating_ip"]
      auto_allocate_ip          = vip.value["auto_allocate_ip"]
      auto_allocate_ip_type     = vip.value["auto_allocate_ip_type"]
      availability_zone         = vip.value["availability_zone"]
      avi_allocated_fip         = vip.value["avi_allocated_fip"]
      avi_allocated_vip         = vip.value["avi_allocated_vip"]
      enabled                   = vip.value["enabled"]
      floating_subnet6_uuid     = vip.value["floating_subnet6_uuid"]
      floating_subnet_uuid      = vip.value["floating_subnet_uuid"]
      network_ref               = vip.value["network_ref"]
      port_uuid                 = vip.value["port_uuid"]
      subnet6_uuid              = vip.value["subnet6_uuid"]
      subnet_uuid               = vip.value["subnet_uuid"]
      vip_id                    = vip.value["vip_id"]

      dynamic "discovered_networks" {
        for_each = vip.value.discovered_networks
        content {
          network_ref = discovered_networks.value["network_ref"]

          dynamic "subnet" {
            for_each = discovered_networks.value.subnet
            content {
              mask = subnet.value["mask"]

              dynamic "ip_addr" {
                for_each = subnet.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "subnet6" {
            for_each = discovered_networks.value.subnet6
            content {
              mask = subnet6.value["mask"]

              dynamic "ip_addr" {
                for_each = subnet6.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "floating_ip" {
        for_each = vip.value.floating_ip
        content {
          addr = floating_ip.value["addr"]
          type = floating_ip.value["type"]
        }
      }

      dynamic "floating_ip6" {
        for_each = vip.value.floating_ip6
        content {
          addr = floating_ip6.value["addr"]
          type = floating_ip6.value["type"]
        }
      }

      dynamic "ip6_address" {
        for_each = vip.value.ip6_address
        content {
          addr = ip6_address.value["addr"]
          type = ip6_address.value["type"]
        }
      }

      dynamic "ip_address" {
        for_each = vip.value.ip_address
        content {
          addr = ip_address.value["addr"]
          type = ip_address.value["type"]
        }
      }

      dynamic "ipam_network_subnet" {
        for_each = vip.value.ipam_network_subnet
        content {
          network_ref  = ipam_network_subnet.value["network_ref"]
          subnet6_uuid = ipam_network_subnet.value["subnet6_uuid"]
          subnet_uuid  = ipam_network_subnet.value["subnet_uuid"]

          dynamic "subnet" {
            for_each = ipam_network_subnet.value.subnet
            content {
              mask = subnet.value["mask"]

              dynamic "ip_addr" {
                for_each = subnet.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "subnet6" {
            for_each = ipam_network_subnet.value.subnet6
            content {
              mask = subnet6.value["mask"]

              dynamic "ip_addr" {
                for_each = subnet6.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "placement_networks" {
        for_each = vip.value.placement_networks
        content {
          network_ref = placement_networks.value["network_ref"]

          dynamic "subnet" {
            for_each = placement_networks.value.subnet
            content {
              mask = subnet.value["mask"]

              dynamic "ip_addr" {
                for_each = subnet.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

          dynamic "subnet6" {
            for_each = placement_networks.value.subnet6
            content {
              mask = subnet6.value["mask"]

              dynamic "ip_addr" {
                for_each = subnet6.value.ip_addr
                content {
                  addr = ip_addr.value["addr"]
                  type = ip_addr.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "subnet" {
        for_each = vip.value.subnet
        content {
          mask = subnet.value["mask"]

          dynamic "ip_addr" {
            for_each = subnet.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

      dynamic "subnet6" {
        for_each = vip.value.subnet6
        content {
          mask = subnet6.value["mask"]

          dynamic "ip_addr" {
            for_each = subnet6.value.ip_addr
            content {
              addr = ip_addr.value["addr"]
              type = ip_addr.value["type"]
            }
          }

        }
      }

    }
  }

  dynamic "vs_datascripts" {
    for_each = var.vs_datascripts
    content {
      index                 = vs_datascripts.value["index"]
      vs_datascript_set_ref = vs_datascripts.value["vs_datascript_set_ref"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "analytics_profile_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.analytics_profile_ref
}

output "apic_contract_graph" {
  description = "returns a string"
  value       = avi_virtualservice.this.apic_contract_graph
}

output "application_profile_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.application_profile_ref
}

output "cloud_config_cksum" {
  description = "returns a string"
  value       = avi_virtualservice.this.cloud_config_cksum
}

output "cloud_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.cloud_ref
}

output "created_by" {
  description = "returns a string"
  value       = avi_virtualservice.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_virtualservice.this.description
}

output "enable_rhi" {
  description = "returns a bool"
  value       = avi_virtualservice.this.enable_rhi
}

output "enable_rhi_snat" {
  description = "returns a bool"
  value       = avi_virtualservice.this.enable_rhi_snat
}

output "error_page_profile_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.error_page_profile_ref
}

output "fqdn" {
  description = "returns a string"
  value       = avi_virtualservice.this.fqdn
}

output "host_name_xlate" {
  description = "returns a string"
  value       = avi_virtualservice.this.host_name_xlate
}

output "id" {
  description = "returns a string"
  value       = avi_virtualservice.this.id
}

output "microservice_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.microservice_ref
}

output "min_pools_up" {
  description = "returns a number"
  value       = avi_virtualservice.this.min_pools_up
}

output "network_profile_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.network_profile_ref
}

output "network_security_policy_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.network_security_policy_ref
}

output "pool_group_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.pool_group_ref
}

output "pool_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.pool_ref
}

output "se_group_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.se_group_ref
}

output "security_policy_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.security_policy_ref
}

output "server_network_profile_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.server_network_profile_ref
}

output "service_metadata" {
  description = "returns a string"
  value       = avi_virtualservice.this.service_metadata
}

output "ssl_profile_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.ssl_profile_ref
}

output "sso_policy_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.sso_policy_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.tenant_ref
}

output "test_se_datastore_level_1_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.test_se_datastore_level_1_ref
}

output "traffic_clone_profile_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.traffic_clone_profile_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_virtualservice.this.uuid
}

output "vh_parent_vs_uuid" {
  description = "returns a string"
  value       = avi_virtualservice.this.vh_parent_vs_uuid
}

output "vrf_context_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.vrf_context_ref
}

output "vsvip_cloud_config_cksum" {
  description = "returns a string"
  value       = avi_virtualservice.this.vsvip_cloud_config_cksum
}

output "vsvip_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.vsvip_ref
}

output "waf_policy_ref" {
  description = "returns a string"
  value       = avi_virtualservice.this.waf_policy_ref
}

output "this" {
  value = avi_virtualservice.this
}
```

[top](#index)