# avi_pool

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
module "avi_pool" {
  source = "./modules/avi/r/avi_pool"

  # analytics_profile_ref - (optional) is a type of string
  analytics_profile_ref = null
  # apic_epg_name - (optional) is a type of string
  apic_epg_name = null
  # application_persistence_profile_ref - (optional) is a type of string
  application_persistence_profile_ref = null
  # autoscale_launch_config_ref - (optional) is a type of string
  autoscale_launch_config_ref = null
  # autoscale_networks - (optional) is a type of list of string
  autoscale_networks = []
  # autoscale_policy_ref - (optional) is a type of string
  autoscale_policy_ref = null
  # capacity_estimation - (optional) is a type of bool
  capacity_estimation = null
  # capacity_estimation_ttfb_thresh - (optional) is a type of number
  capacity_estimation_ttfb_thresh = null
  # cloud_config_cksum - (optional) is a type of string
  cloud_config_cksum = null
  # cloud_ref - (optional) is a type of string
  cloud_ref = null
  # connection_ramp_duration - (optional) is a type of number
  connection_ramp_duration = null
  # created_by - (optional) is a type of string
  created_by = null
  # default_server_port - (optional) is a type of number
  default_server_port = null
  # delete_server_on_dns_refresh - (optional) is a type of bool
  delete_server_on_dns_refresh = null
  # description - (optional) is a type of string
  description = null
  # domain_name - (optional) is a type of list of string
  domain_name = []
  # east_west - (optional) is a type of bool
  east_west = null
  # enabled - (optional) is a type of bool
  enabled = null
  # external_autoscale_groups - (optional) is a type of list of string
  external_autoscale_groups = []
  # fewest_tasks_feedback_delay - (optional) is a type of number
  fewest_tasks_feedback_delay = null
  # graceful_disable_timeout - (optional) is a type of number
  graceful_disable_timeout = null
  # health_monitor_refs - (optional) is a type of list of string
  health_monitor_refs = []
  # host_check_enabled - (optional) is a type of bool
  host_check_enabled = null
  # ignore_servers - (optional) is a type of bool
  ignore_servers = null
  # inline_health_monitor - (optional) is a type of bool
  inline_health_monitor = null
  # ipaddrgroup_ref - (optional) is a type of string
  ipaddrgroup_ref = null
  # lb_algorithm - (optional) is a type of string
  lb_algorithm = null
  # lb_algorithm_consistent_hash_hdr - (optional) is a type of string
  lb_algorithm_consistent_hash_hdr = null
  # lb_algorithm_core_nonaffinity - (optional) is a type of number
  lb_algorithm_core_nonaffinity = null
  # lb_algorithm_hash - (optional) is a type of string
  lb_algorithm_hash = null
  # lookup_server_by_name - (optional) is a type of bool
  lookup_server_by_name = null
  # max_concurrent_connections_per_server - (optional) is a type of number
  max_concurrent_connections_per_server = null
  # min_health_monitors_up - (optional) is a type of number
  min_health_monitors_up = null
  # min_servers_up - (optional) is a type of number
  min_servers_up = null
  # name - (required) is a type of string
  name = null
  # nsx_securitygroup - (optional) is a type of list of string
  nsx_securitygroup = []
  # pki_profile_ref - (optional) is a type of string
  pki_profile_ref = null
  # request_queue_depth - (optional) is a type of number
  request_queue_depth = null
  # request_queue_enabled - (optional) is a type of bool
  request_queue_enabled = null
  # rewrite_host_header_to_server_name - (optional) is a type of bool
  rewrite_host_header_to_server_name = null
  # rewrite_host_header_to_sni - (optional) is a type of bool
  rewrite_host_header_to_sni = null
  # server_name - (optional) is a type of string
  server_name = null
  # server_timeout - (optional) is a type of number
  server_timeout = null
  # service_metadata - (optional) is a type of string
  service_metadata = null
  # sni_enabled - (optional) is a type of bool
  sni_enabled = null
  # ssl_key_and_certificate_ref - (optional) is a type of string
  ssl_key_and_certificate_ref = null
  # ssl_profile_ref - (optional) is a type of string
  ssl_profile_ref = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # use_service_port - (optional) is a type of bool
  use_service_port = null
  # uuid - (optional) is a type of string
  uuid = null
  # vrf_ref - (optional) is a type of string
  vrf_ref = null

  analytics_policy = [{
    enable_realtime_metrics = null
  }]

  conn_pool_properties = [{
    upstream_connpool_conn_idle_tmo    = null
    upstream_connpool_conn_life_tmo    = null
    upstream_connpool_conn_max_reuse   = null
    upstream_connpool_server_max_cache = null
  }]

  fail_action = [{
    local_rsp = [{
      file = [{
        content_type = null
        file_content = null
      }]
      status_code = null
    }]
    redirect = [{
      host        = null
      path        = null
      protocol    = null
      query       = null
      status_code = null
    }]
    type = null
  }]

  max_conn_rate_per_server = [{
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

  networks = [{
    network_ref   = null
    server_filter = null
  }]

  placement_networks = [{
    network_ref = null
    subnet = [{
      ip_addr = [{
        addr = null
        type = null
      }]
      mask = null
    }]
  }]

  server_reselect = [{
    enabled             = null
    num_retries         = null
    retry_nonidempotent = null
    retry_timeout       = null
    svr_resp_code = [{
      codes = []
      ranges = [{
        begin = null
        end   = null
      }]
      resp_code_block = []
    }]
  }]

  servers = [{
    autoscaling_group_name = null
    availability_zone      = null
    description            = null
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
    enabled                   = null
    external_orchestration_id = null
    external_uuid             = null
    hostname                  = null
    ip = [{
      addr = null
      type = null
    }]
    location = [{
      latitude  = null
      longitude = null
      name      = null
      tag       = null
    }]
    mac_address           = null
    nw_ref                = null
    port                  = null
    prst_hdr_val          = null
    ratio                 = null
    resolve_server_by_dns = null
    rewrite_host_header   = null
    server_node           = null
    static                = null
    verify_network        = null
    vm_ref                = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "analytics_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "apic_epg_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_persistence_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autoscale_launch_config_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "autoscale_networks" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "autoscale_policy_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capacity_estimation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "capacity_estimation_ttfb_thresh" {
  description = "(optional)"
  type        = number
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

variable "connection_ramp_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "created_by" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_server_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "delete_server_on_dns_refresh" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "east_west" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "external_autoscale_groups" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "fewest_tasks_feedback_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "graceful_disable_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_monitor_refs" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "host_check_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ignore_servers" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "inline_health_monitor" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ipaddrgroup_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lb_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lb_algorithm_consistent_hash_hdr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lb_algorithm_core_nonaffinity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lb_algorithm_hash" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "lookup_server_by_name" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "max_concurrent_connections_per_server" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_health_monitors_up" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "min_servers_up" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "nsx_securitygroup" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "pki_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_queue_depth" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "request_queue_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "rewrite_host_header_to_server_name" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "rewrite_host_header_to_sni" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "server_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_metadata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sni_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ssl_key_and_certificate_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_profile_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "use_service_port" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrf_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "analytics_policy" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      enable_realtime_metrics = bool
    }
  ))
  default = []
}

variable "conn_pool_properties" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      upstream_connpool_conn_idle_tmo    = number
      upstream_connpool_conn_life_tmo    = number
      upstream_connpool_conn_max_reuse   = number
      upstream_connpool_server_max_cache = number
    }
  ))
  default = []
}

variable "fail_action" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      local_rsp = set(object(
        {
          file = set(object(
            {
              content_type = string
              file_content = string
            }
          ))
          status_code = string
        }
      ))
      redirect = set(object(
        {
          host        = string
          path        = string
          protocol    = string
          query       = string
          status_code = string
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "max_conn_rate_per_server" {
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

variable "networks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      network_ref   = string
      server_filter = string
    }
  ))
  default = []
}

variable "placement_networks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
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
    }
  ))
  default = []
}

variable "server_reselect" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      enabled             = bool
      num_retries         = number
      retry_nonidempotent = bool
      retry_timeout       = number
      svr_resp_code = set(object(
        {
          codes = list(number)
          ranges = list(object(
            {
              begin = number
              end   = number
            }
          ))
          resp_code_block = list(string)
        }
      ))
    }
  ))
  default = []
}

variable "servers" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      autoscaling_group_name = string
      availability_zone      = string
      description            = string
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
      enabled                   = bool
      external_orchestration_id = string
      external_uuid             = string
      hostname                  = string
      ip = set(object(
        {
          addr = string
          type = string
        }
      ))
      location = set(object(
        {
          latitude  = number
          longitude = number
          name      = string
          tag       = string
        }
      ))
      mac_address           = string
      nw_ref                = string
      port                  = number
      prst_hdr_val          = string
      ratio                 = number
      resolve_server_by_dns = bool
      rewrite_host_header   = bool
      server_node           = string
      static                = bool
      verify_network        = bool
      vm_ref                = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_pool" "this" {
  analytics_profile_ref                 = var.analytics_profile_ref
  apic_epg_name                         = var.apic_epg_name
  application_persistence_profile_ref   = var.application_persistence_profile_ref
  autoscale_launch_config_ref           = var.autoscale_launch_config_ref
  autoscale_networks                    = var.autoscale_networks
  autoscale_policy_ref                  = var.autoscale_policy_ref
  capacity_estimation                   = var.capacity_estimation
  capacity_estimation_ttfb_thresh       = var.capacity_estimation_ttfb_thresh
  cloud_config_cksum                    = var.cloud_config_cksum
  cloud_ref                             = var.cloud_ref
  connection_ramp_duration              = var.connection_ramp_duration
  created_by                            = var.created_by
  default_server_port                   = var.default_server_port
  delete_server_on_dns_refresh          = var.delete_server_on_dns_refresh
  description                           = var.description
  domain_name                           = var.domain_name
  east_west                             = var.east_west
  enabled                               = var.enabled
  external_autoscale_groups             = var.external_autoscale_groups
  fewest_tasks_feedback_delay           = var.fewest_tasks_feedback_delay
  graceful_disable_timeout              = var.graceful_disable_timeout
  health_monitor_refs                   = var.health_monitor_refs
  host_check_enabled                    = var.host_check_enabled
  ignore_servers                        = var.ignore_servers
  inline_health_monitor                 = var.inline_health_monitor
  ipaddrgroup_ref                       = var.ipaddrgroup_ref
  lb_algorithm                          = var.lb_algorithm
  lb_algorithm_consistent_hash_hdr      = var.lb_algorithm_consistent_hash_hdr
  lb_algorithm_core_nonaffinity         = var.lb_algorithm_core_nonaffinity
  lb_algorithm_hash                     = var.lb_algorithm_hash
  lookup_server_by_name                 = var.lookup_server_by_name
  max_concurrent_connections_per_server = var.max_concurrent_connections_per_server
  min_health_monitors_up                = var.min_health_monitors_up
  min_servers_up                        = var.min_servers_up
  name                                  = var.name
  nsx_securitygroup                     = var.nsx_securitygroup
  pki_profile_ref                       = var.pki_profile_ref
  request_queue_depth                   = var.request_queue_depth
  request_queue_enabled                 = var.request_queue_enabled
  rewrite_host_header_to_server_name    = var.rewrite_host_header_to_server_name
  rewrite_host_header_to_sni            = var.rewrite_host_header_to_sni
  server_name                           = var.server_name
  server_timeout                        = var.server_timeout
  service_metadata                      = var.service_metadata
  sni_enabled                           = var.sni_enabled
  ssl_key_and_certificate_ref           = var.ssl_key_and_certificate_ref
  ssl_profile_ref                       = var.ssl_profile_ref
  tenant_ref                            = var.tenant_ref
  use_service_port                      = var.use_service_port
  uuid                                  = var.uuid
  vrf_ref                               = var.vrf_ref

  dynamic "analytics_policy" {
    for_each = var.analytics_policy
    content {
      enable_realtime_metrics = analytics_policy.value["enable_realtime_metrics"]
    }
  }

  dynamic "conn_pool_properties" {
    for_each = var.conn_pool_properties
    content {
      upstream_connpool_conn_idle_tmo    = conn_pool_properties.value["upstream_connpool_conn_idle_tmo"]
      upstream_connpool_conn_life_tmo    = conn_pool_properties.value["upstream_connpool_conn_life_tmo"]
      upstream_connpool_conn_max_reuse   = conn_pool_properties.value["upstream_connpool_conn_max_reuse"]
      upstream_connpool_server_max_cache = conn_pool_properties.value["upstream_connpool_server_max_cache"]
    }
  }

  dynamic "fail_action" {
    for_each = var.fail_action
    content {
      type = fail_action.value["type"]

      dynamic "local_rsp" {
        for_each = fail_action.value.local_rsp
        content {
          status_code = local_rsp.value["status_code"]

          dynamic "file" {
            for_each = local_rsp.value.file
            content {
              content_type = file.value["content_type"]
              file_content = file.value["file_content"]
            }
          }

        }
      }

      dynamic "redirect" {
        for_each = fail_action.value.redirect
        content {
          host        = redirect.value["host"]
          path        = redirect.value["path"]
          protocol    = redirect.value["protocol"]
          query       = redirect.value["query"]
          status_code = redirect.value["status_code"]
        }
      }

    }
  }

  dynamic "max_conn_rate_per_server" {
    for_each = var.max_conn_rate_per_server
    content {
      explicit_tracking = max_conn_rate_per_server.value["explicit_tracking"]
      fine_grain        = max_conn_rate_per_server.value["fine_grain"]
      http_cookie       = max_conn_rate_per_server.value["http_cookie"]
      http_header       = max_conn_rate_per_server.value["http_header"]

      dynamic "action" {
        for_each = max_conn_rate_per_server.value.action
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
        for_each = max_conn_rate_per_server.value.rate_limiter
        content {
          burst_sz = rate_limiter.value["burst_sz"]
          count    = rate_limiter.value["count"]
          name     = rate_limiter.value["name"]
          period   = rate_limiter.value["period"]
        }
      }

    }
  }

  dynamic "networks" {
    for_each = var.networks
    content {
      network_ref   = networks.value["network_ref"]
      server_filter = networks.value["server_filter"]
    }
  }

  dynamic "placement_networks" {
    for_each = var.placement_networks
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

    }
  }

  dynamic "server_reselect" {
    for_each = var.server_reselect
    content {
      enabled             = server_reselect.value["enabled"]
      num_retries         = server_reselect.value["num_retries"]
      retry_nonidempotent = server_reselect.value["retry_nonidempotent"]
      retry_timeout       = server_reselect.value["retry_timeout"]

      dynamic "svr_resp_code" {
        for_each = server_reselect.value.svr_resp_code
        content {
          codes           = svr_resp_code.value["codes"]
          resp_code_block = svr_resp_code.value["resp_code_block"]

          dynamic "ranges" {
            for_each = svr_resp_code.value.ranges
            content {
              begin = ranges.value["begin"]
              end   = ranges.value["end"]
            }
          }

        }
      }

    }
  }

  dynamic "servers" {
    for_each = var.servers
    content {
      autoscaling_group_name    = servers.value["autoscaling_group_name"]
      availability_zone         = servers.value["availability_zone"]
      description               = servers.value["description"]
      enabled                   = servers.value["enabled"]
      external_orchestration_id = servers.value["external_orchestration_id"]
      external_uuid             = servers.value["external_uuid"]
      hostname                  = servers.value["hostname"]
      mac_address               = servers.value["mac_address"]
      nw_ref                    = servers.value["nw_ref"]
      port                      = servers.value["port"]
      prst_hdr_val              = servers.value["prst_hdr_val"]
      ratio                     = servers.value["ratio"]
      resolve_server_by_dns     = servers.value["resolve_server_by_dns"]
      rewrite_host_header       = servers.value["rewrite_host_header"]
      server_node               = servers.value["server_node"]
      static                    = servers.value["static"]
      verify_network            = servers.value["verify_network"]
      vm_ref                    = servers.value["vm_ref"]

      dynamic "discovered_networks" {
        for_each = servers.value.discovered_networks
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

      dynamic "ip" {
        for_each = servers.value.ip
        content {
          addr = ip.value["addr"]
          type = ip.value["type"]
        }
      }

      dynamic "location" {
        for_each = servers.value.location
        content {
          latitude  = location.value["latitude"]
          longitude = location.value["longitude"]
          name      = location.value["name"]
          tag       = location.value["tag"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "analytics_profile_ref" {
  description = "returns a string"
  value       = avi_pool.this.analytics_profile_ref
}

output "application_persistence_profile_ref" {
  description = "returns a string"
  value       = avi_pool.this.application_persistence_profile_ref
}

output "autoscale_launch_config_ref" {
  description = "returns a string"
  value       = avi_pool.this.autoscale_launch_config_ref
}

output "autoscale_policy_ref" {
  description = "returns a string"
  value       = avi_pool.this.autoscale_policy_ref
}

output "cloud_ref" {
  description = "returns a string"
  value       = avi_pool.this.cloud_ref
}

output "health_monitor_refs" {
  description = "returns a list of string"
  value       = avi_pool.this.health_monitor_refs
}

output "id" {
  description = "returns a string"
  value       = avi_pool.this.id
}

output "ipaddrgroup_ref" {
  description = "returns a string"
  value       = avi_pool.this.ipaddrgroup_ref
}

output "pki_profile_ref" {
  description = "returns a string"
  value       = avi_pool.this.pki_profile_ref
}

output "ssl_key_and_certificate_ref" {
  description = "returns a string"
  value       = avi_pool.this.ssl_key_and_certificate_ref
}

output "ssl_profile_ref" {
  description = "returns a string"
  value       = avi_pool.this.ssl_profile_ref
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_pool.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = avi_pool.this.uuid
}

output "vrf_ref" {
  description = "returns a string"
  value       = avi_pool.this.vrf_ref
}

output "this" {
  value = avi_pool.this
}
```

[top](#index)