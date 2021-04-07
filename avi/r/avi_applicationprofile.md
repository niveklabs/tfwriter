# avi_applicationprofile

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
module "avi_applicationprofile" {
  source = "./modules/avi/r/avi_applicationprofile"

  # cloud_config_cksum - (optional) is a type of string
  cloud_config_cksum = null
  # created_by - (optional) is a type of string
  created_by = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # preserve_client_ip - (optional) is a type of bool
  preserve_client_ip = null
  # preserve_client_port - (optional) is a type of bool
  preserve_client_port = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # type - (required) is a type of string
  type = null
  # uuid - (optional) is a type of string
  uuid = null

  dns_service_profile = [{
    aaaa_empty_response  = null
    admin_email          = null
    dns_over_tcp_enabled = null
    dns_zones = [{
      admin_email = null
      domain_name = null
      name_server = null
    }]
    domain_names                  = []
    ecs_stripping_enabled         = null
    edns                          = null
    edns_client_subnet_prefix_len = null
    error_response                = null
    name_server                   = null
    negative_caching_ttl          = null
    num_dns_ip                    = null
    ttl                           = null
  }]

  dos_rl_profile = [{
    dos_profile = [{
      thresh_info = [{
        attack    = null
        max_value = null
        min_value = null
      }]
      thresh_period = null
    }]
    rl_profile = [{
      client_ip_connections_rate_limit = [{
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
      client_ip_failed_requests_rate_limit = [{
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
      client_ip_requests_rate_limit = [{
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
      client_ip_scanners_requests_rate_limit = [{
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
      client_ip_to_uri_failed_requests_rate_limit = [{
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
      client_ip_to_uri_requests_rate_limit = [{
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
      custom_requests_rate_limit = [{
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
      http_header_rate_limits = [{
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
      uri_failed_requests_rate_limit = [{
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
      uri_requests_rate_limit = [{
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
      uri_scanners_requests_rate_limit = [{
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
    }]
  }]

  http_profile = [{
    allow_dots_in_header_name = null
    cache_config = [{
      age_header                   = null
      aggressive                   = null
      date_header                  = null
      default_expire               = null
      enabled                      = null
      heuristic_expire             = null
      ignore_request_cache_control = null
      max_cache_size               = null
      max_object_size              = null
      mime_types_black_group_refs  = []
      mime_types_black_list        = []
      mime_types_group_refs        = []
      mime_types_list              = []
      min_object_size              = null
      query_cacheable              = null
      uri_non_cacheable = [{
        match_case        = null
        match_criteria    = null
        match_str         = []
        string_group_refs = []
      }]
      xcache_header = null
    }]
    client_body_timeout     = null
    client_header_timeout   = null
    client_max_body_size    = null
    client_max_header_size  = null
    client_max_request_size = null
    compression_profile = [{
      compressible_content_ref = null
      compression              = null
      filter = [{
        devices_ref = null
        index       = null
        ip_addr_prefixes = [{
          ip_addr = [{
            addr = null
            type = null
          }]
          mask = null
        }]
        ip_addr_ranges = [{
          begin = [{
            addr = null
            type = null
          }]
          end = [{
            addr = null
            type = null
          }]
        }]
        ip_addrs = [{
          addr = null
          type = null
        }]
        ip_addrs_ref = null
        level        = null
        match        = null
        name         = null
        user_agent   = []
      }]
      remove_accept_encoding_header = null
      type                          = null
    }]
    connection_multiplexing_enabled                  = null
    disable_keepalive_posts_msie6                    = null
    disable_sni_hostname_check                       = null
    enable_chunk_merge                               = null
    enable_fire_and_forget                           = null
    enable_request_body_buffering                    = null
    enable_request_body_metrics                      = null
    fwd_close_hdr_for_bound_connections              = null
    hsts_enabled                                     = null
    hsts_max_age                                     = null
    hsts_subdomains_enabled                          = null
    http2_enabled                                    = null
    http_to_https                                    = null
    httponly_enabled                                 = null
    keepalive_header                                 = null
    keepalive_timeout                                = null
    max_bad_rps_cip                                  = null
    max_bad_rps_cip_uri                              = null
    max_bad_rps_uri                                  = null
    max_http2_concurrent_streams_per_connection      = null
    max_http2_control_frames_per_connection          = null
    max_http2_empty_data_frames_per_connection       = null
    max_http2_queued_frames_to_client_per_connection = null
    max_keepalive_requests                           = null
    max_response_headers_size                        = null
    max_rps_cip                                      = null
    max_rps_cip_uri                                  = null
    max_rps_unknown_cip                              = null
    max_rps_unknown_uri                              = null
    max_rps_uri                                      = null
    pki_profile_ref                                  = null
    post_accept_timeout                              = null
    reset_conn_http_on_ssl_port                      = null
    respond_with_100_continue                        = null
    secure_cookie_enabled                            = null
    server_side_redirect_to_https                    = null
    ssl_client_certificate_action = [{
      close_connection = null
      headers = [{
        request_header       = null
        request_header_value = null
      }]
    }]
    ssl_client_certificate_mode = null
    use_app_keepalive_timeout   = null
    websockets_enabled          = null
    x_forwarded_proto_enabled   = null
    xff_alternate_name          = null
    xff_enabled                 = null
  }]

  sip_service_profile = [{
    transaction_timeout = null
  }]

  tcp_app_profile = [{
    pki_profile_ref             = null
    proxy_protocol_enabled      = null
    proxy_protocol_version      = null
    ssl_client_certificate_mode = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cloud_config_cksum" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "preserve_client_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "preserve_client_port" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_service_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      aaaa_empty_response  = bool
      admin_email          = string
      dns_over_tcp_enabled = bool
      dns_zones = list(object(
        {
          admin_email = string
          domain_name = string
          name_server = string
        }
      ))
      domain_names                  = list(string)
      ecs_stripping_enabled         = bool
      edns                          = bool
      edns_client_subnet_prefix_len = number
      error_response                = string
      name_server                   = string
      negative_caching_ttl          = number
      num_dns_ip                    = number
      ttl                           = number
    }
  ))
  default = []
}

variable "dos_rl_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      dos_profile = set(object(
        {
          thresh_info = list(object(
            {
              attack    = string
              max_value = number
              min_value = number
            }
          ))
          thresh_period = number
        }
      ))
      rl_profile = set(object(
        {
          client_ip_connections_rate_limit = set(object(
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
          client_ip_failed_requests_rate_limit = set(object(
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
          client_ip_requests_rate_limit = set(object(
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
          client_ip_scanners_requests_rate_limit = set(object(
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
          client_ip_to_uri_failed_requests_rate_limit = set(object(
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
          client_ip_to_uri_requests_rate_limit = set(object(
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
          custom_requests_rate_limit = set(object(
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
          http_header_rate_limits = list(object(
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
          uri_failed_requests_rate_limit = set(object(
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
          uri_requests_rate_limit = set(object(
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
          uri_scanners_requests_rate_limit = set(object(
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
        }
      ))
    }
  ))
  default = []
}

variable "http_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      allow_dots_in_header_name = bool
      cache_config = set(object(
        {
          age_header                   = bool
          aggressive                   = bool
          date_header                  = bool
          default_expire               = number
          enabled                      = bool
          heuristic_expire             = bool
          ignore_request_cache_control = bool
          max_cache_size               = number
          max_object_size              = number
          mime_types_black_group_refs  = list(string)
          mime_types_black_list        = list(string)
          mime_types_group_refs        = list(string)
          mime_types_list              = list(string)
          min_object_size              = number
          query_cacheable              = bool
          uri_non_cacheable = set(object(
            {
              match_case        = string
              match_criteria    = string
              match_str         = list(string)
              string_group_refs = list(string)
            }
          ))
          xcache_header = bool
        }
      ))
      client_body_timeout     = number
      client_header_timeout   = number
      client_max_body_size    = number
      client_max_header_size  = number
      client_max_request_size = number
      compression_profile = set(object(
        {
          compressible_content_ref = string
          compression              = bool
          filter = list(object(
            {
              devices_ref = string
              index       = number
              ip_addr_prefixes = list(object(
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
              ip_addr_ranges = list(object(
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
              ip_addrs = list(object(
                {
                  addr = string
                  type = string
                }
              ))
              ip_addrs_ref = string
              level        = string
              match        = string
              name         = string
              user_agent   = list(string)
            }
          ))
          remove_accept_encoding_header = bool
          type                          = string
        }
      ))
      connection_multiplexing_enabled                  = bool
      disable_keepalive_posts_msie6                    = bool
      disable_sni_hostname_check                       = bool
      enable_chunk_merge                               = bool
      enable_fire_and_forget                           = bool
      enable_request_body_buffering                    = bool
      enable_request_body_metrics                      = bool
      fwd_close_hdr_for_bound_connections              = bool
      hsts_enabled                                     = bool
      hsts_max_age                                     = number
      hsts_subdomains_enabled                          = bool
      http2_enabled                                    = bool
      http_to_https                                    = bool
      httponly_enabled                                 = bool
      keepalive_header                                 = bool
      keepalive_timeout                                = number
      max_bad_rps_cip                                  = number
      max_bad_rps_cip_uri                              = number
      max_bad_rps_uri                                  = number
      max_http2_concurrent_streams_per_connection      = number
      max_http2_control_frames_per_connection          = number
      max_http2_empty_data_frames_per_connection       = number
      max_http2_queued_frames_to_client_per_connection = number
      max_keepalive_requests                           = number
      max_response_headers_size                        = number
      max_rps_cip                                      = number
      max_rps_cip_uri                                  = number
      max_rps_unknown_cip                              = number
      max_rps_unknown_uri                              = number
      max_rps_uri                                      = number
      pki_profile_ref                                  = string
      post_accept_timeout                              = number
      reset_conn_http_on_ssl_port                      = bool
      respond_with_100_continue                        = bool
      secure_cookie_enabled                            = bool
      server_side_redirect_to_https                    = bool
      ssl_client_certificate_action = set(object(
        {
          close_connection = bool
          headers = list(object(
            {
              request_header       = string
              request_header_value = string
            }
          ))
        }
      ))
      ssl_client_certificate_mode = string
      use_app_keepalive_timeout   = bool
      websockets_enabled          = bool
      x_forwarded_proto_enabled   = bool
      xff_alternate_name          = string
      xff_enabled                 = bool
    }
  ))
  default = []
}

variable "sip_service_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      transaction_timeout = number
    }
  ))
  default = []
}

variable "tcp_app_profile" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      pki_profile_ref             = string
      proxy_protocol_enabled      = bool
      proxy_protocol_version      = string
      ssl_client_certificate_mode = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_applicationprofile" "this" {
  # cloud_config_cksum - (optional) is a type of string
  cloud_config_cksum = var.cloud_config_cksum
  # created_by - (optional) is a type of string
  created_by = var.created_by
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # preserve_client_ip - (optional) is a type of bool
  preserve_client_ip = var.preserve_client_ip
  # preserve_client_port - (optional) is a type of bool
  preserve_client_port = var.preserve_client_port
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # type - (required) is a type of string
  type = var.type
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "dns_service_profile" {
    for_each = var.dns_service_profile
    content {
      # aaaa_empty_response - (optional) is a type of bool
      aaaa_empty_response = dns_service_profile.value["aaaa_empty_response"]
      # admin_email - (optional) is a type of string
      admin_email = dns_service_profile.value["admin_email"]
      # dns_over_tcp_enabled - (optional) is a type of bool
      dns_over_tcp_enabled = dns_service_profile.value["dns_over_tcp_enabled"]
      # domain_names - (optional) is a type of list of string
      domain_names = dns_service_profile.value["domain_names"]
      # ecs_stripping_enabled - (optional) is a type of bool
      ecs_stripping_enabled = dns_service_profile.value["ecs_stripping_enabled"]
      # edns - (optional) is a type of bool
      edns = dns_service_profile.value["edns"]
      # edns_client_subnet_prefix_len - (optional) is a type of number
      edns_client_subnet_prefix_len = dns_service_profile.value["edns_client_subnet_prefix_len"]
      # error_response - (optional) is a type of string
      error_response = dns_service_profile.value["error_response"]
      # name_server - (optional) is a type of string
      name_server = dns_service_profile.value["name_server"]
      # negative_caching_ttl - (optional) is a type of number
      negative_caching_ttl = dns_service_profile.value["negative_caching_ttl"]
      # num_dns_ip - (optional) is a type of number
      num_dns_ip = dns_service_profile.value["num_dns_ip"]
      # ttl - (optional) is a type of number
      ttl = dns_service_profile.value["ttl"]

      dynamic "dns_zones" {
        for_each = dns_service_profile.value.dns_zones
        content {
          # admin_email - (optional) is a type of string
          admin_email = dns_zones.value["admin_email"]
          # domain_name - (optional) is a type of string
          domain_name = dns_zones.value["domain_name"]
          # name_server - (optional) is a type of string
          name_server = dns_zones.value["name_server"]
        }
      }

    }
  }

  dynamic "dos_rl_profile" {
    for_each = var.dos_rl_profile
    content {

      dynamic "dos_profile" {
        for_each = dos_rl_profile.value.dos_profile
        content {
          # thresh_period - (required) is a type of number
          thresh_period = dos_profile.value["thresh_period"]

          dynamic "thresh_info" {
            for_each = dos_profile.value.thresh_info
            content {
              # attack - (required) is a type of string
              attack = thresh_info.value["attack"]
              # max_value - (required) is a type of number
              max_value = thresh_info.value["max_value"]
              # min_value - (required) is a type of number
              min_value = thresh_info.value["min_value"]
            }
          }

        }
      }

      dynamic "rl_profile" {
        for_each = dos_rl_profile.value.rl_profile
        content {

          dynamic "client_ip_connections_rate_limit" {
            for_each = rl_profile.value.client_ip_connections_rate_limit
            content {
              # explicit_tracking - (optional) is a type of bool
              explicit_tracking = client_ip_connections_rate_limit.value["explicit_tracking"]
              # fine_grain - (optional) is a type of bool
              fine_grain = client_ip_connections_rate_limit.value["fine_grain"]
              # http_cookie - (optional) is a type of string
              http_cookie = client_ip_connections_rate_limit.value["http_cookie"]
              # http_header - (optional) is a type of string
              http_header = client_ip_connections_rate_limit.value["http_header"]

              dynamic "action" {
                for_each = client_ip_connections_rate_limit.value.action
                content {
                  # status_code - (optional) is a type of string
                  status_code = action.value["status_code"]
                  # type - (optional) is a type of string
                  type = action.value["type"]

                  dynamic "file" {
                    for_each = action.value.file
                    content {
                      # content_type - (required) is a type of string
                      content_type = file.value["content_type"]
                      # file_content - (required) is a type of string
                      file_content = file.value["file_content"]
                    }
                  }

                  dynamic "redirect" {
                    for_each = action.value.redirect
                    content {
                      # keep_query - (optional) is a type of bool
                      keep_query = redirect.value["keep_query"]
                      # port - (optional) is a type of number
                      port = redirect.value["port"]
                      # protocol - (required) is a type of string
                      protocol = redirect.value["protocol"]
                      # status_code - (optional) is a type of string
                      status_code = redirect.value["status_code"]

                      dynamic "host" {
                        for_each = redirect.value.host
                        content {
                          # type - (required) is a type of string
                          type = host.value["type"]

                          dynamic "tokens" {
                            for_each = host.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "path" {
                        for_each = redirect.value.path
                        content {
                          # type - (required) is a type of string
                          type = path.value["type"]

                          dynamic "tokens" {
                            for_each = path.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "rate_limiter" {
                for_each = client_ip_connections_rate_limit.value.rate_limiter
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter.value["period"]
                }
              }

            }
          }

          dynamic "client_ip_failed_requests_rate_limit" {
            for_each = rl_profile.value.client_ip_failed_requests_rate_limit
            content {
              # explicit_tracking - (optional) is a type of bool
              explicit_tracking = client_ip_failed_requests_rate_limit.value["explicit_tracking"]
              # fine_grain - (optional) is a type of bool
              fine_grain = client_ip_failed_requests_rate_limit.value["fine_grain"]
              # http_cookie - (optional) is a type of string
              http_cookie = client_ip_failed_requests_rate_limit.value["http_cookie"]
              # http_header - (optional) is a type of string
              http_header = client_ip_failed_requests_rate_limit.value["http_header"]

              dynamic "action" {
                for_each = client_ip_failed_requests_rate_limit.value.action
                content {
                  # status_code - (optional) is a type of string
                  status_code = action.value["status_code"]
                  # type - (optional) is a type of string
                  type = action.value["type"]

                  dynamic "file" {
                    for_each = action.value.file
                    content {
                      # content_type - (required) is a type of string
                      content_type = file.value["content_type"]
                      # file_content - (required) is a type of string
                      file_content = file.value["file_content"]
                    }
                  }

                  dynamic "redirect" {
                    for_each = action.value.redirect
                    content {
                      # keep_query - (optional) is a type of bool
                      keep_query = redirect.value["keep_query"]
                      # port - (optional) is a type of number
                      port = redirect.value["port"]
                      # protocol - (required) is a type of string
                      protocol = redirect.value["protocol"]
                      # status_code - (optional) is a type of string
                      status_code = redirect.value["status_code"]

                      dynamic "host" {
                        for_each = redirect.value.host
                        content {
                          # type - (required) is a type of string
                          type = host.value["type"]

                          dynamic "tokens" {
                            for_each = host.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "path" {
                        for_each = redirect.value.path
                        content {
                          # type - (required) is a type of string
                          type = path.value["type"]

                          dynamic "tokens" {
                            for_each = path.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "rate_limiter" {
                for_each = client_ip_failed_requests_rate_limit.value.rate_limiter
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter.value["period"]
                }
              }

            }
          }

          dynamic "client_ip_requests_rate_limit" {
            for_each = rl_profile.value.client_ip_requests_rate_limit
            content {
              # explicit_tracking - (optional) is a type of bool
              explicit_tracking = client_ip_requests_rate_limit.value["explicit_tracking"]
              # fine_grain - (optional) is a type of bool
              fine_grain = client_ip_requests_rate_limit.value["fine_grain"]
              # http_cookie - (optional) is a type of string
              http_cookie = client_ip_requests_rate_limit.value["http_cookie"]
              # http_header - (optional) is a type of string
              http_header = client_ip_requests_rate_limit.value["http_header"]

              dynamic "action" {
                for_each = client_ip_requests_rate_limit.value.action
                content {
                  # status_code - (optional) is a type of string
                  status_code = action.value["status_code"]
                  # type - (optional) is a type of string
                  type = action.value["type"]

                  dynamic "file" {
                    for_each = action.value.file
                    content {
                      # content_type - (required) is a type of string
                      content_type = file.value["content_type"]
                      # file_content - (required) is a type of string
                      file_content = file.value["file_content"]
                    }
                  }

                  dynamic "redirect" {
                    for_each = action.value.redirect
                    content {
                      # keep_query - (optional) is a type of bool
                      keep_query = redirect.value["keep_query"]
                      # port - (optional) is a type of number
                      port = redirect.value["port"]
                      # protocol - (required) is a type of string
                      protocol = redirect.value["protocol"]
                      # status_code - (optional) is a type of string
                      status_code = redirect.value["status_code"]

                      dynamic "host" {
                        for_each = redirect.value.host
                        content {
                          # type - (required) is a type of string
                          type = host.value["type"]

                          dynamic "tokens" {
                            for_each = host.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "path" {
                        for_each = redirect.value.path
                        content {
                          # type - (required) is a type of string
                          type = path.value["type"]

                          dynamic "tokens" {
                            for_each = path.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "rate_limiter" {
                for_each = client_ip_requests_rate_limit.value.rate_limiter
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter.value["period"]
                }
              }

            }
          }

          dynamic "client_ip_scanners_requests_rate_limit" {
            for_each = rl_profile.value.client_ip_scanners_requests_rate_limit
            content {
              # explicit_tracking - (optional) is a type of bool
              explicit_tracking = client_ip_scanners_requests_rate_limit.value["explicit_tracking"]
              # fine_grain - (optional) is a type of bool
              fine_grain = client_ip_scanners_requests_rate_limit.value["fine_grain"]
              # http_cookie - (optional) is a type of string
              http_cookie = client_ip_scanners_requests_rate_limit.value["http_cookie"]
              # http_header - (optional) is a type of string
              http_header = client_ip_scanners_requests_rate_limit.value["http_header"]

              dynamic "action" {
                for_each = client_ip_scanners_requests_rate_limit.value.action
                content {
                  # status_code - (optional) is a type of string
                  status_code = action.value["status_code"]
                  # type - (optional) is a type of string
                  type = action.value["type"]

                  dynamic "file" {
                    for_each = action.value.file
                    content {
                      # content_type - (required) is a type of string
                      content_type = file.value["content_type"]
                      # file_content - (required) is a type of string
                      file_content = file.value["file_content"]
                    }
                  }

                  dynamic "redirect" {
                    for_each = action.value.redirect
                    content {
                      # keep_query - (optional) is a type of bool
                      keep_query = redirect.value["keep_query"]
                      # port - (optional) is a type of number
                      port = redirect.value["port"]
                      # protocol - (required) is a type of string
                      protocol = redirect.value["protocol"]
                      # status_code - (optional) is a type of string
                      status_code = redirect.value["status_code"]

                      dynamic "host" {
                        for_each = redirect.value.host
                        content {
                          # type - (required) is a type of string
                          type = host.value["type"]

                          dynamic "tokens" {
                            for_each = host.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "path" {
                        for_each = redirect.value.path
                        content {
                          # type - (required) is a type of string
                          type = path.value["type"]

                          dynamic "tokens" {
                            for_each = path.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "rate_limiter" {
                for_each = client_ip_scanners_requests_rate_limit.value.rate_limiter
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter.value["period"]
                }
              }

            }
          }

          dynamic "client_ip_to_uri_failed_requests_rate_limit" {
            for_each = rl_profile.value.client_ip_to_uri_failed_requests_rate_limit
            content {
              # explicit_tracking - (optional) is a type of bool
              explicit_tracking = client_ip_to_uri_failed_requests_rate_limit.value["explicit_tracking"]
              # fine_grain - (optional) is a type of bool
              fine_grain = client_ip_to_uri_failed_requests_rate_limit.value["fine_grain"]
              # http_cookie - (optional) is a type of string
              http_cookie = client_ip_to_uri_failed_requests_rate_limit.value["http_cookie"]
              # http_header - (optional) is a type of string
              http_header = client_ip_to_uri_failed_requests_rate_limit.value["http_header"]

              dynamic "action" {
                for_each = client_ip_to_uri_failed_requests_rate_limit.value.action
                content {
                  # status_code - (optional) is a type of string
                  status_code = action.value["status_code"]
                  # type - (optional) is a type of string
                  type = action.value["type"]

                  dynamic "file" {
                    for_each = action.value.file
                    content {
                      # content_type - (required) is a type of string
                      content_type = file.value["content_type"]
                      # file_content - (required) is a type of string
                      file_content = file.value["file_content"]
                    }
                  }

                  dynamic "redirect" {
                    for_each = action.value.redirect
                    content {
                      # keep_query - (optional) is a type of bool
                      keep_query = redirect.value["keep_query"]
                      # port - (optional) is a type of number
                      port = redirect.value["port"]
                      # protocol - (required) is a type of string
                      protocol = redirect.value["protocol"]
                      # status_code - (optional) is a type of string
                      status_code = redirect.value["status_code"]

                      dynamic "host" {
                        for_each = redirect.value.host
                        content {
                          # type - (required) is a type of string
                          type = host.value["type"]

                          dynamic "tokens" {
                            for_each = host.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "path" {
                        for_each = redirect.value.path
                        content {
                          # type - (required) is a type of string
                          type = path.value["type"]

                          dynamic "tokens" {
                            for_each = path.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "rate_limiter" {
                for_each = client_ip_to_uri_failed_requests_rate_limit.value.rate_limiter
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter.value["period"]
                }
              }

            }
          }

          dynamic "client_ip_to_uri_requests_rate_limit" {
            for_each = rl_profile.value.client_ip_to_uri_requests_rate_limit
            content {
              # explicit_tracking - (optional) is a type of bool
              explicit_tracking = client_ip_to_uri_requests_rate_limit.value["explicit_tracking"]
              # fine_grain - (optional) is a type of bool
              fine_grain = client_ip_to_uri_requests_rate_limit.value["fine_grain"]
              # http_cookie - (optional) is a type of string
              http_cookie = client_ip_to_uri_requests_rate_limit.value["http_cookie"]
              # http_header - (optional) is a type of string
              http_header = client_ip_to_uri_requests_rate_limit.value["http_header"]

              dynamic "action" {
                for_each = client_ip_to_uri_requests_rate_limit.value.action
                content {
                  # status_code - (optional) is a type of string
                  status_code = action.value["status_code"]
                  # type - (optional) is a type of string
                  type = action.value["type"]

                  dynamic "file" {
                    for_each = action.value.file
                    content {
                      # content_type - (required) is a type of string
                      content_type = file.value["content_type"]
                      # file_content - (required) is a type of string
                      file_content = file.value["file_content"]
                    }
                  }

                  dynamic "redirect" {
                    for_each = action.value.redirect
                    content {
                      # keep_query - (optional) is a type of bool
                      keep_query = redirect.value["keep_query"]
                      # port - (optional) is a type of number
                      port = redirect.value["port"]
                      # protocol - (required) is a type of string
                      protocol = redirect.value["protocol"]
                      # status_code - (optional) is a type of string
                      status_code = redirect.value["status_code"]

                      dynamic "host" {
                        for_each = redirect.value.host
                        content {
                          # type - (required) is a type of string
                          type = host.value["type"]

                          dynamic "tokens" {
                            for_each = host.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "path" {
                        for_each = redirect.value.path
                        content {
                          # type - (required) is a type of string
                          type = path.value["type"]

                          dynamic "tokens" {
                            for_each = path.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "rate_limiter" {
                for_each = client_ip_to_uri_requests_rate_limit.value.rate_limiter
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter.value["period"]
                }
              }

            }
          }

          dynamic "custom_requests_rate_limit" {
            for_each = rl_profile.value.custom_requests_rate_limit
            content {
              # explicit_tracking - (optional) is a type of bool
              explicit_tracking = custom_requests_rate_limit.value["explicit_tracking"]
              # fine_grain - (optional) is a type of bool
              fine_grain = custom_requests_rate_limit.value["fine_grain"]
              # http_cookie - (optional) is a type of string
              http_cookie = custom_requests_rate_limit.value["http_cookie"]
              # http_header - (optional) is a type of string
              http_header = custom_requests_rate_limit.value["http_header"]

              dynamic "action" {
                for_each = custom_requests_rate_limit.value.action
                content {
                  # status_code - (optional) is a type of string
                  status_code = action.value["status_code"]
                  # type - (optional) is a type of string
                  type = action.value["type"]

                  dynamic "file" {
                    for_each = action.value.file
                    content {
                      # content_type - (required) is a type of string
                      content_type = file.value["content_type"]
                      # file_content - (required) is a type of string
                      file_content = file.value["file_content"]
                    }
                  }

                  dynamic "redirect" {
                    for_each = action.value.redirect
                    content {
                      # keep_query - (optional) is a type of bool
                      keep_query = redirect.value["keep_query"]
                      # port - (optional) is a type of number
                      port = redirect.value["port"]
                      # protocol - (required) is a type of string
                      protocol = redirect.value["protocol"]
                      # status_code - (optional) is a type of string
                      status_code = redirect.value["status_code"]

                      dynamic "host" {
                        for_each = redirect.value.host
                        content {
                          # type - (required) is a type of string
                          type = host.value["type"]

                          dynamic "tokens" {
                            for_each = host.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "path" {
                        for_each = redirect.value.path
                        content {
                          # type - (required) is a type of string
                          type = path.value["type"]

                          dynamic "tokens" {
                            for_each = path.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "rate_limiter" {
                for_each = custom_requests_rate_limit.value.rate_limiter
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter.value["period"]
                }
              }

            }
          }

          dynamic "http_header_rate_limits" {
            for_each = rl_profile.value.http_header_rate_limits
            content {
              # explicit_tracking - (optional) is a type of bool
              explicit_tracking = http_header_rate_limits.value["explicit_tracking"]
              # fine_grain - (optional) is a type of bool
              fine_grain = http_header_rate_limits.value["fine_grain"]
              # http_cookie - (optional) is a type of string
              http_cookie = http_header_rate_limits.value["http_cookie"]
              # http_header - (optional) is a type of string
              http_header = http_header_rate_limits.value["http_header"]

              dynamic "action" {
                for_each = http_header_rate_limits.value.action
                content {
                  # status_code - (optional) is a type of string
                  status_code = action.value["status_code"]
                  # type - (optional) is a type of string
                  type = action.value["type"]

                  dynamic "file" {
                    for_each = action.value.file
                    content {
                      # content_type - (required) is a type of string
                      content_type = file.value["content_type"]
                      # file_content - (required) is a type of string
                      file_content = file.value["file_content"]
                    }
                  }

                  dynamic "redirect" {
                    for_each = action.value.redirect
                    content {
                      # keep_query - (optional) is a type of bool
                      keep_query = redirect.value["keep_query"]
                      # port - (optional) is a type of number
                      port = redirect.value["port"]
                      # protocol - (required) is a type of string
                      protocol = redirect.value["protocol"]
                      # status_code - (optional) is a type of string
                      status_code = redirect.value["status_code"]

                      dynamic "host" {
                        for_each = redirect.value.host
                        content {
                          # type - (required) is a type of string
                          type = host.value["type"]

                          dynamic "tokens" {
                            for_each = host.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "path" {
                        for_each = redirect.value.path
                        content {
                          # type - (required) is a type of string
                          type = path.value["type"]

                          dynamic "tokens" {
                            for_each = path.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "rate_limiter" {
                for_each = http_header_rate_limits.value.rate_limiter
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter.value["period"]
                }
              }

            }
          }

          dynamic "uri_failed_requests_rate_limit" {
            for_each = rl_profile.value.uri_failed_requests_rate_limit
            content {
              # explicit_tracking - (optional) is a type of bool
              explicit_tracking = uri_failed_requests_rate_limit.value["explicit_tracking"]
              # fine_grain - (optional) is a type of bool
              fine_grain = uri_failed_requests_rate_limit.value["fine_grain"]
              # http_cookie - (optional) is a type of string
              http_cookie = uri_failed_requests_rate_limit.value["http_cookie"]
              # http_header - (optional) is a type of string
              http_header = uri_failed_requests_rate_limit.value["http_header"]

              dynamic "action" {
                for_each = uri_failed_requests_rate_limit.value.action
                content {
                  # status_code - (optional) is a type of string
                  status_code = action.value["status_code"]
                  # type - (optional) is a type of string
                  type = action.value["type"]

                  dynamic "file" {
                    for_each = action.value.file
                    content {
                      # content_type - (required) is a type of string
                      content_type = file.value["content_type"]
                      # file_content - (required) is a type of string
                      file_content = file.value["file_content"]
                    }
                  }

                  dynamic "redirect" {
                    for_each = action.value.redirect
                    content {
                      # keep_query - (optional) is a type of bool
                      keep_query = redirect.value["keep_query"]
                      # port - (optional) is a type of number
                      port = redirect.value["port"]
                      # protocol - (required) is a type of string
                      protocol = redirect.value["protocol"]
                      # status_code - (optional) is a type of string
                      status_code = redirect.value["status_code"]

                      dynamic "host" {
                        for_each = redirect.value.host
                        content {
                          # type - (required) is a type of string
                          type = host.value["type"]

                          dynamic "tokens" {
                            for_each = host.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "path" {
                        for_each = redirect.value.path
                        content {
                          # type - (required) is a type of string
                          type = path.value["type"]

                          dynamic "tokens" {
                            for_each = path.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "rate_limiter" {
                for_each = uri_failed_requests_rate_limit.value.rate_limiter
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter.value["period"]
                }
              }

            }
          }

          dynamic "uri_requests_rate_limit" {
            for_each = rl_profile.value.uri_requests_rate_limit
            content {
              # explicit_tracking - (optional) is a type of bool
              explicit_tracking = uri_requests_rate_limit.value["explicit_tracking"]
              # fine_grain - (optional) is a type of bool
              fine_grain = uri_requests_rate_limit.value["fine_grain"]
              # http_cookie - (optional) is a type of string
              http_cookie = uri_requests_rate_limit.value["http_cookie"]
              # http_header - (optional) is a type of string
              http_header = uri_requests_rate_limit.value["http_header"]

              dynamic "action" {
                for_each = uri_requests_rate_limit.value.action
                content {
                  # status_code - (optional) is a type of string
                  status_code = action.value["status_code"]
                  # type - (optional) is a type of string
                  type = action.value["type"]

                  dynamic "file" {
                    for_each = action.value.file
                    content {
                      # content_type - (required) is a type of string
                      content_type = file.value["content_type"]
                      # file_content - (required) is a type of string
                      file_content = file.value["file_content"]
                    }
                  }

                  dynamic "redirect" {
                    for_each = action.value.redirect
                    content {
                      # keep_query - (optional) is a type of bool
                      keep_query = redirect.value["keep_query"]
                      # port - (optional) is a type of number
                      port = redirect.value["port"]
                      # protocol - (required) is a type of string
                      protocol = redirect.value["protocol"]
                      # status_code - (optional) is a type of string
                      status_code = redirect.value["status_code"]

                      dynamic "host" {
                        for_each = redirect.value.host
                        content {
                          # type - (required) is a type of string
                          type = host.value["type"]

                          dynamic "tokens" {
                            for_each = host.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "path" {
                        for_each = redirect.value.path
                        content {
                          # type - (required) is a type of string
                          type = path.value["type"]

                          dynamic "tokens" {
                            for_each = path.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "rate_limiter" {
                for_each = uri_requests_rate_limit.value.rate_limiter
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter.value["period"]
                }
              }

            }
          }

          dynamic "uri_scanners_requests_rate_limit" {
            for_each = rl_profile.value.uri_scanners_requests_rate_limit
            content {
              # explicit_tracking - (optional) is a type of bool
              explicit_tracking = uri_scanners_requests_rate_limit.value["explicit_tracking"]
              # fine_grain - (optional) is a type of bool
              fine_grain = uri_scanners_requests_rate_limit.value["fine_grain"]
              # http_cookie - (optional) is a type of string
              http_cookie = uri_scanners_requests_rate_limit.value["http_cookie"]
              # http_header - (optional) is a type of string
              http_header = uri_scanners_requests_rate_limit.value["http_header"]

              dynamic "action" {
                for_each = uri_scanners_requests_rate_limit.value.action
                content {
                  # status_code - (optional) is a type of string
                  status_code = action.value["status_code"]
                  # type - (optional) is a type of string
                  type = action.value["type"]

                  dynamic "file" {
                    for_each = action.value.file
                    content {
                      # content_type - (required) is a type of string
                      content_type = file.value["content_type"]
                      # file_content - (required) is a type of string
                      file_content = file.value["file_content"]
                    }
                  }

                  dynamic "redirect" {
                    for_each = action.value.redirect
                    content {
                      # keep_query - (optional) is a type of bool
                      keep_query = redirect.value["keep_query"]
                      # port - (optional) is a type of number
                      port = redirect.value["port"]
                      # protocol - (required) is a type of string
                      protocol = redirect.value["protocol"]
                      # status_code - (optional) is a type of string
                      status_code = redirect.value["status_code"]

                      dynamic "host" {
                        for_each = redirect.value.host
                        content {
                          # type - (required) is a type of string
                          type = host.value["type"]

                          dynamic "tokens" {
                            for_each = host.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                      dynamic "path" {
                        for_each = redirect.value.path
                        content {
                          # type - (required) is a type of string
                          type = path.value["type"]

                          dynamic "tokens" {
                            for_each = path.value.tokens
                            content {
                              # end_index - (optional) is a type of number
                              end_index = tokens.value["end_index"]
                              # start_index - (optional) is a type of number
                              start_index = tokens.value["start_index"]
                              # str_value - (optional) is a type of string
                              str_value = tokens.value["str_value"]
                              # type - (required) is a type of string
                              type = tokens.value["type"]
                            }
                          }

                        }
                      }

                    }
                  }

                }
              }

              dynamic "rate_limiter" {
                for_each = uri_scanners_requests_rate_limit.value.rate_limiter
                content {
                  # burst_sz - (optional) is a type of number
                  burst_sz = rate_limiter.value["burst_sz"]
                  # count - (optional) is a type of number
                  count = rate_limiter.value["count"]
                  # name - (optional) is a type of string
                  name = rate_limiter.value["name"]
                  # period - (optional) is a type of number
                  period = rate_limiter.value["period"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "http_profile" {
    for_each = var.http_profile
    content {
      # allow_dots_in_header_name - (optional) is a type of bool
      allow_dots_in_header_name = http_profile.value["allow_dots_in_header_name"]
      # client_body_timeout - (optional) is a type of number
      client_body_timeout = http_profile.value["client_body_timeout"]
      # client_header_timeout - (optional) is a type of number
      client_header_timeout = http_profile.value["client_header_timeout"]
      # client_max_body_size - (optional) is a type of number
      client_max_body_size = http_profile.value["client_max_body_size"]
      # client_max_header_size - (optional) is a type of number
      client_max_header_size = http_profile.value["client_max_header_size"]
      # client_max_request_size - (optional) is a type of number
      client_max_request_size = http_profile.value["client_max_request_size"]
      # connection_multiplexing_enabled - (optional) is a type of bool
      connection_multiplexing_enabled = http_profile.value["connection_multiplexing_enabled"]
      # disable_keepalive_posts_msie6 - (optional) is a type of bool
      disable_keepalive_posts_msie6 = http_profile.value["disable_keepalive_posts_msie6"]
      # disable_sni_hostname_check - (optional) is a type of bool
      disable_sni_hostname_check = http_profile.value["disable_sni_hostname_check"]
      # enable_chunk_merge - (optional) is a type of bool
      enable_chunk_merge = http_profile.value["enable_chunk_merge"]
      # enable_fire_and_forget - (optional) is a type of bool
      enable_fire_and_forget = http_profile.value["enable_fire_and_forget"]
      # enable_request_body_buffering - (optional) is a type of bool
      enable_request_body_buffering = http_profile.value["enable_request_body_buffering"]
      # enable_request_body_metrics - (optional) is a type of bool
      enable_request_body_metrics = http_profile.value["enable_request_body_metrics"]
      # fwd_close_hdr_for_bound_connections - (optional) is a type of bool
      fwd_close_hdr_for_bound_connections = http_profile.value["fwd_close_hdr_for_bound_connections"]
      # hsts_enabled - (optional) is a type of bool
      hsts_enabled = http_profile.value["hsts_enabled"]
      # hsts_max_age - (optional) is a type of number
      hsts_max_age = http_profile.value["hsts_max_age"]
      # hsts_subdomains_enabled - (optional) is a type of bool
      hsts_subdomains_enabled = http_profile.value["hsts_subdomains_enabled"]
      # http2_enabled - (optional) is a type of bool
      http2_enabled = http_profile.value["http2_enabled"]
      # http_to_https - (optional) is a type of bool
      http_to_https = http_profile.value["http_to_https"]
      # httponly_enabled - (optional) is a type of bool
      httponly_enabled = http_profile.value["httponly_enabled"]
      # keepalive_header - (optional) is a type of bool
      keepalive_header = http_profile.value["keepalive_header"]
      # keepalive_timeout - (optional) is a type of number
      keepalive_timeout = http_profile.value["keepalive_timeout"]
      # max_bad_rps_cip - (optional) is a type of number
      max_bad_rps_cip = http_profile.value["max_bad_rps_cip"]
      # max_bad_rps_cip_uri - (optional) is a type of number
      max_bad_rps_cip_uri = http_profile.value["max_bad_rps_cip_uri"]
      # max_bad_rps_uri - (optional) is a type of number
      max_bad_rps_uri = http_profile.value["max_bad_rps_uri"]
      # max_http2_concurrent_streams_per_connection - (optional) is a type of number
      max_http2_concurrent_streams_per_connection = http_profile.value["max_http2_concurrent_streams_per_connection"]
      # max_http2_control_frames_per_connection - (optional) is a type of number
      max_http2_control_frames_per_connection = http_profile.value["max_http2_control_frames_per_connection"]
      # max_http2_empty_data_frames_per_connection - (optional) is a type of number
      max_http2_empty_data_frames_per_connection = http_profile.value["max_http2_empty_data_frames_per_connection"]
      # max_http2_queued_frames_to_client_per_connection - (optional) is a type of number
      max_http2_queued_frames_to_client_per_connection = http_profile.value["max_http2_queued_frames_to_client_per_connection"]
      # max_keepalive_requests - (optional) is a type of number
      max_keepalive_requests = http_profile.value["max_keepalive_requests"]
      # max_response_headers_size - (optional) is a type of number
      max_response_headers_size = http_profile.value["max_response_headers_size"]
      # max_rps_cip - (optional) is a type of number
      max_rps_cip = http_profile.value["max_rps_cip"]
      # max_rps_cip_uri - (optional) is a type of number
      max_rps_cip_uri = http_profile.value["max_rps_cip_uri"]
      # max_rps_unknown_cip - (optional) is a type of number
      max_rps_unknown_cip = http_profile.value["max_rps_unknown_cip"]
      # max_rps_unknown_uri - (optional) is a type of number
      max_rps_unknown_uri = http_profile.value["max_rps_unknown_uri"]
      # max_rps_uri - (optional) is a type of number
      max_rps_uri = http_profile.value["max_rps_uri"]
      # pki_profile_ref - (optional) is a type of string
      pki_profile_ref = http_profile.value["pki_profile_ref"]
      # post_accept_timeout - (optional) is a type of number
      post_accept_timeout = http_profile.value["post_accept_timeout"]
      # reset_conn_http_on_ssl_port - (optional) is a type of bool
      reset_conn_http_on_ssl_port = http_profile.value["reset_conn_http_on_ssl_port"]
      # respond_with_100_continue - (optional) is a type of bool
      respond_with_100_continue = http_profile.value["respond_with_100_continue"]
      # secure_cookie_enabled - (optional) is a type of bool
      secure_cookie_enabled = http_profile.value["secure_cookie_enabled"]
      # server_side_redirect_to_https - (optional) is a type of bool
      server_side_redirect_to_https = http_profile.value["server_side_redirect_to_https"]
      # ssl_client_certificate_mode - (optional) is a type of string
      ssl_client_certificate_mode = http_profile.value["ssl_client_certificate_mode"]
      # use_app_keepalive_timeout - (optional) is a type of bool
      use_app_keepalive_timeout = http_profile.value["use_app_keepalive_timeout"]
      # websockets_enabled - (optional) is a type of bool
      websockets_enabled = http_profile.value["websockets_enabled"]
      # x_forwarded_proto_enabled - (optional) is a type of bool
      x_forwarded_proto_enabled = http_profile.value["x_forwarded_proto_enabled"]
      # xff_alternate_name - (optional) is a type of string
      xff_alternate_name = http_profile.value["xff_alternate_name"]
      # xff_enabled - (optional) is a type of bool
      xff_enabled = http_profile.value["xff_enabled"]

      dynamic "cache_config" {
        for_each = http_profile.value.cache_config
        content {
          # age_header - (optional) is a type of bool
          age_header = cache_config.value["age_header"]
          # aggressive - (optional) is a type of bool
          aggressive = cache_config.value["aggressive"]
          # date_header - (optional) is a type of bool
          date_header = cache_config.value["date_header"]
          # default_expire - (optional) is a type of number
          default_expire = cache_config.value["default_expire"]
          # enabled - (optional) is a type of bool
          enabled = cache_config.value["enabled"]
          # heuristic_expire - (optional) is a type of bool
          heuristic_expire = cache_config.value["heuristic_expire"]
          # ignore_request_cache_control - (optional) is a type of bool
          ignore_request_cache_control = cache_config.value["ignore_request_cache_control"]
          # max_cache_size - (optional) is a type of number
          max_cache_size = cache_config.value["max_cache_size"]
          # max_object_size - (optional) is a type of number
          max_object_size = cache_config.value["max_object_size"]
          # mime_types_black_group_refs - (optional) is a type of list of string
          mime_types_black_group_refs = cache_config.value["mime_types_black_group_refs"]
          # mime_types_black_list - (optional) is a type of list of string
          mime_types_black_list = cache_config.value["mime_types_black_list"]
          # mime_types_group_refs - (optional) is a type of list of string
          mime_types_group_refs = cache_config.value["mime_types_group_refs"]
          # mime_types_list - (optional) is a type of list of string
          mime_types_list = cache_config.value["mime_types_list"]
          # min_object_size - (optional) is a type of number
          min_object_size = cache_config.value["min_object_size"]
          # query_cacheable - (optional) is a type of bool
          query_cacheable = cache_config.value["query_cacheable"]
          # xcache_header - (optional) is a type of bool
          xcache_header = cache_config.value["xcache_header"]

          dynamic "uri_non_cacheable" {
            for_each = cache_config.value.uri_non_cacheable
            content {
              # match_case - (optional) is a type of string
              match_case = uri_non_cacheable.value["match_case"]
              # match_criteria - (required) is a type of string
              match_criteria = uri_non_cacheable.value["match_criteria"]
              # match_str - (optional) is a type of list of string
              match_str = uri_non_cacheable.value["match_str"]
              # string_group_refs - (optional) is a type of list of string
              string_group_refs = uri_non_cacheable.value["string_group_refs"]
            }
          }

        }
      }

      dynamic "compression_profile" {
        for_each = http_profile.value.compression_profile
        content {
          # compressible_content_ref - (optional) is a type of string
          compressible_content_ref = compression_profile.value["compressible_content_ref"]
          # compression - (required) is a type of bool
          compression = compression_profile.value["compression"]
          # remove_accept_encoding_header - (required) is a type of bool
          remove_accept_encoding_header = compression_profile.value["remove_accept_encoding_header"]
          # type - (required) is a type of string
          type = compression_profile.value["type"]

          dynamic "filter" {
            for_each = compression_profile.value.filter
            content {
              # devices_ref - (optional) is a type of string
              devices_ref = filter.value["devices_ref"]
              # index - (required) is a type of number
              index = filter.value["index"]
              # ip_addrs_ref - (optional) is a type of string
              ip_addrs_ref = filter.value["ip_addrs_ref"]
              # level - (required) is a type of string
              level = filter.value["level"]
              # match - (optional) is a type of string
              match = filter.value["match"]
              # name - (required) is a type of string
              name = filter.value["name"]
              # user_agent - (optional) is a type of list of string
              user_agent = filter.value["user_agent"]

              dynamic "ip_addr_prefixes" {
                for_each = filter.value.ip_addr_prefixes
                content {
                  # mask - (required) is a type of number
                  mask = ip_addr_prefixes.value["mask"]

                  dynamic "ip_addr" {
                    for_each = ip_addr_prefixes.value.ip_addr
                    content {
                      # addr - (required) is a type of string
                      addr = ip_addr.value["addr"]
                      # type - (required) is a type of string
                      type = ip_addr.value["type"]
                    }
                  }

                }
              }

              dynamic "ip_addr_ranges" {
                for_each = filter.value.ip_addr_ranges
                content {

                  dynamic "begin" {
                    for_each = ip_addr_ranges.value.begin
                    content {
                      # addr - (required) is a type of string
                      addr = begin.value["addr"]
                      # type - (required) is a type of string
                      type = begin.value["type"]
                    }
                  }

                  dynamic "end" {
                    for_each = ip_addr_ranges.value.end
                    content {
                      # addr - (required) is a type of string
                      addr = end.value["addr"]
                      # type - (required) is a type of string
                      type = end.value["type"]
                    }
                  }

                }
              }

              dynamic "ip_addrs" {
                for_each = filter.value.ip_addrs
                content {
                  # addr - (required) is a type of string
                  addr = ip_addrs.value["addr"]
                  # type - (required) is a type of string
                  type = ip_addrs.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "ssl_client_certificate_action" {
        for_each = http_profile.value.ssl_client_certificate_action
        content {
          # close_connection - (optional) is a type of bool
          close_connection = ssl_client_certificate_action.value["close_connection"]

          dynamic "headers" {
            for_each = ssl_client_certificate_action.value.headers
            content {
              # request_header - (optional) is a type of string
              request_header = headers.value["request_header"]
              # request_header_value - (optional) is a type of string
              request_header_value = headers.value["request_header_value"]
            }
          }

        }
      }

    }
  }

  dynamic "sip_service_profile" {
    for_each = var.sip_service_profile
    content {
      # transaction_timeout - (optional) is a type of number
      transaction_timeout = sip_service_profile.value["transaction_timeout"]
    }
  }

  dynamic "tcp_app_profile" {
    for_each = var.tcp_app_profile
    content {
      # pki_profile_ref - (optional) is a type of string
      pki_profile_ref = tcp_app_profile.value["pki_profile_ref"]
      # proxy_protocol_enabled - (optional) is a type of bool
      proxy_protocol_enabled = tcp_app_profile.value["proxy_protocol_enabled"]
      # proxy_protocol_version - (optional) is a type of string
      proxy_protocol_version = tcp_app_profile.value["proxy_protocol_version"]
      # ssl_client_certificate_mode - (optional) is a type of string
      ssl_client_certificate_mode = tcp_app_profile.value["ssl_client_certificate_mode"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cloud_config_cksum" {
  description = "returns a string"
  value       = avi_applicationprofile.this.cloud_config_cksum
}

output "created_by" {
  description = "returns a string"
  value       = avi_applicationprofile.this.created_by
}

output "description" {
  description = "returns a string"
  value       = avi_applicationprofile.this.description
}

output "id" {
  description = "returns a string"
  value       = avi_applicationprofile.this.id
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_applicationprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_applicationprofile.this.uuid
}

output "this" {
  value = avi_applicationprofile.this
}
```

[top](#index)