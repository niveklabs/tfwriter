# thunder_slb_template_policy

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_slb_template_policy" {
  source = "./modules/thunder/r/thunder_slb_template_policy"

  # bw_list_name - (optional) is a type of string
  bw_list_name = null
  # full_domain_tree - (optional) is a type of number
  full_domain_tree = null
  # interval - (optional) is a type of number
  interval = null
  # name - (optional) is a type of string
  name = null
  # over_limit - (optional) is a type of number
  over_limit = null
  # over_limit_lockup - (optional) is a type of number
  over_limit_lockup = null
  # over_limit_logging - (optional) is a type of number
  over_limit_logging = null
  # over_limit_reset - (optional) is a type of number
  over_limit_reset = null
  # overlap - (optional) is a type of number
  overlap = null
  # share - (optional) is a type of number
  share = null
  # timeout - (optional) is a type of number
  timeout = null
  # use_destination_ip - (optional) is a type of number
  use_destination_ip = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  bw_list_id = [{
    action_interval = null
    bw_list_action  = null
    fail            = null
    id              = null
    logging_drp_rst = null
    pbslb_interval  = null
    pbslb_logging   = null
    service_group   = null
  }]

  class_list = [{
    client_ip_l3_dest   = null
    client_ip_l7_header = null
    header_name         = null
    lid_list = [{
      action_value           = null
      bw_per                 = null
      bw_rate_limit          = null
      conn_limit             = null
      conn_per               = null
      conn_rate_limit        = null
      direct_action          = null
      direct_action_interval = null
      direct_action_value    = null
      direct_fail            = null
      direct_logging_drp_rst = null
      direct_pbslb_interval  = null
      direct_pbslb_logging   = null
      direct_service_group   = null
      dns64 = [{
        disable          = null
        exclusive_answer = null
        prefix           = null
      }]
      interval           = null
      lidnum             = null
      lockout            = null
      log                = null
      over_limit_action  = null
      request_limit      = null
      request_per        = null
      request_rate_limit = null
      response_code_rate_limit = [{
        code_range_end   = null
        code_range_start = null
        period           = null
        threshold        = null
      }]
      user_tag = null
      uuid     = null
    }]
    name = null
    uuid = null
  }]

  forward_policy = [{
    acos_event_log = null
    action_list = [{
      action1            = null
      drop_message       = null
      drop_redirect_url  = null
      drop_response_code = null
      fake_sg            = null
      fall_back          = null
      fall_back_snat     = null
      forward_snat       = null
      http_status_code   = null
      log                = null
      name               = null
      real_sg            = null
      sampling_enable = [{
        counters1 = null
      }]
      user_tag = null
      uuid     = null
    }]
    filtering = [{
      ssli_url_filtering = null
    }]
    local_logging        = null
    no_client_conn_reuse = null
    require_web_category = null
    san_filtering = [{
      ssli_url_filtering_san = null
    }]
    source_list = [{
      destination = [{
        any = [{
          action = null
          sampling_enable = [{
            counters1 = null
          }]
          uuid = null
        }]
        class_list_list = [{
          action          = null
          dest_class_list = null
          priority        = null
          sampling_enable = [{
            counters1 = null
          }]
          type = null
          uuid = null
        }]
        web_category_list_list = [{
          action   = null
          priority = null
          sampling_enable = [{
            counters1 = null
          }]
          type              = null
          uuid              = null
          web_category_list = null
        }]
      }]
      match_any              = null
      match_authorize_policy = null
      match_class_list       = null
      name                   = null
      priority               = null
      sampling_enable = [{
        counters1 = null
      }]
      user_tag = null
      uuid     = null
    }]
    uuid = null
  }]

  sampling_enable = [{
    counters1 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bw_list_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "full_domain_tree" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "over_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "over_limit_lockup" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "over_limit_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "over_limit_reset" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "overlap" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "share" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_destination_ip" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bw_list_id" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action_interval = number
      bw_list_action  = string
      fail            = number
      id              = number
      logging_drp_rst = number
      pbslb_interval  = number
      pbslb_logging   = number
      service_group   = string
    }
  ))
  default = []
}

variable "class_list" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      client_ip_l3_dest   = number
      client_ip_l7_header = number
      header_name         = string
      lid_list = list(object(
        {
          action_value           = string
          bw_per                 = number
          bw_rate_limit          = number
          conn_limit             = number
          conn_per               = number
          conn_rate_limit        = number
          direct_action          = number
          direct_action_interval = number
          direct_action_value    = string
          direct_fail            = number
          direct_logging_drp_rst = number
          direct_pbslb_interval  = number
          direct_pbslb_logging   = number
          direct_service_group   = string
          dns64 = list(object(
            {
              disable          = number
              exclusive_answer = number
              prefix           = string
            }
          ))
          interval           = number
          lidnum             = number
          lockout            = number
          log                = number
          over_limit_action  = number
          request_limit      = number
          request_per        = number
          request_rate_limit = number
          response_code_rate_limit = list(object(
            {
              code_range_end   = number
              code_range_start = number
              period           = number
              threshold        = number
            }
          ))
          user_tag = string
          uuid     = string
        }
      ))
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "forward_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      acos_event_log = number
      action_list = list(object(
        {
          action1            = string
          drop_message       = string
          drop_redirect_url  = string
          drop_response_code = number
          fake_sg            = string
          fall_back          = string
          fall_back_snat     = string
          forward_snat       = string
          http_status_code   = string
          log                = number
          name               = string
          real_sg            = string
          sampling_enable = list(object(
            {
              counters1 = string
            }
          ))
          user_tag = string
          uuid     = string
        }
      ))
      filtering = list(object(
        {
          ssli_url_filtering = string
        }
      ))
      local_logging        = number
      no_client_conn_reuse = number
      require_web_category = number
      san_filtering = list(object(
        {
          ssli_url_filtering_san = string
        }
      ))
      source_list = list(object(
        {
          destination = list(object(
            {
              any = list(object(
                {
                  action = string
                  sampling_enable = list(object(
                    {
                      counters1 = string
                    }
                  ))
                  uuid = string
                }
              ))
              class_list_list = list(object(
                {
                  action          = string
                  dest_class_list = string
                  priority        = number
                  sampling_enable = list(object(
                    {
                      counters1 = string
                    }
                  ))
                  type = string
                  uuid = string
                }
              ))
              web_category_list_list = list(object(
                {
                  action   = string
                  priority = number
                  sampling_enable = list(object(
                    {
                      counters1 = string
                    }
                  ))
                  type              = string
                  uuid              = string
                  web_category_list = string
                }
              ))
            }
          ))
          match_any              = number
          match_authorize_policy = string
          match_class_list       = string
          name                   = string
          priority               = number
          sampling_enable = list(object(
            {
              counters1 = string
            }
          ))
          user_tag = string
          uuid     = string
        }
      ))
      uuid = string
    }
  ))
  default = []
}

variable "sampling_enable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      counters1 = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_policy" "this" {
  bw_list_name       = var.bw_list_name
  full_domain_tree   = var.full_domain_tree
  interval           = var.interval
  name               = var.name
  over_limit         = var.over_limit
  over_limit_lockup  = var.over_limit_lockup
  over_limit_logging = var.over_limit_logging
  over_limit_reset   = var.over_limit_reset
  overlap            = var.overlap
  share              = var.share
  timeout            = var.timeout
  use_destination_ip = var.use_destination_ip
  user_tag           = var.user_tag
  uuid               = var.uuid

  dynamic "bw_list_id" {
    for_each = var.bw_list_id
    content {
      action_interval = bw_list_id.value["action_interval"]
      bw_list_action  = bw_list_id.value["bw_list_action"]
      fail            = bw_list_id.value["fail"]
      id              = bw_list_id.value["id"]
      logging_drp_rst = bw_list_id.value["logging_drp_rst"]
      pbslb_interval  = bw_list_id.value["pbslb_interval"]
      pbslb_logging   = bw_list_id.value["pbslb_logging"]
      service_group   = bw_list_id.value["service_group"]
    }
  }

  dynamic "class_list" {
    for_each = var.class_list
    content {
      client_ip_l3_dest   = class_list.value["client_ip_l3_dest"]
      client_ip_l7_header = class_list.value["client_ip_l7_header"]
      header_name         = class_list.value["header_name"]
      name                = class_list.value["name"]
      uuid                = class_list.value["uuid"]

      dynamic "lid_list" {
        for_each = class_list.value.lid_list
        content {
          action_value           = lid_list.value["action_value"]
          bw_per                 = lid_list.value["bw_per"]
          bw_rate_limit          = lid_list.value["bw_rate_limit"]
          conn_limit             = lid_list.value["conn_limit"]
          conn_per               = lid_list.value["conn_per"]
          conn_rate_limit        = lid_list.value["conn_rate_limit"]
          direct_action          = lid_list.value["direct_action"]
          direct_action_interval = lid_list.value["direct_action_interval"]
          direct_action_value    = lid_list.value["direct_action_value"]
          direct_fail            = lid_list.value["direct_fail"]
          direct_logging_drp_rst = lid_list.value["direct_logging_drp_rst"]
          direct_pbslb_interval  = lid_list.value["direct_pbslb_interval"]
          direct_pbslb_logging   = lid_list.value["direct_pbslb_logging"]
          direct_service_group   = lid_list.value["direct_service_group"]
          interval               = lid_list.value["interval"]
          lidnum                 = lid_list.value["lidnum"]
          lockout                = lid_list.value["lockout"]
          log                    = lid_list.value["log"]
          over_limit_action      = lid_list.value["over_limit_action"]
          request_limit          = lid_list.value["request_limit"]
          request_per            = lid_list.value["request_per"]
          request_rate_limit     = lid_list.value["request_rate_limit"]
          user_tag               = lid_list.value["user_tag"]
          uuid                   = lid_list.value["uuid"]

          dynamic "dns64" {
            for_each = lid_list.value.dns64
            content {
              disable          = dns64.value["disable"]
              exclusive_answer = dns64.value["exclusive_answer"]
              prefix           = dns64.value["prefix"]
            }
          }

          dynamic "response_code_rate_limit" {
            for_each = lid_list.value.response_code_rate_limit
            content {
              code_range_end   = response_code_rate_limit.value["code_range_end"]
              code_range_start = response_code_rate_limit.value["code_range_start"]
              period           = response_code_rate_limit.value["period"]
              threshold        = response_code_rate_limit.value["threshold"]
            }
          }

        }
      }

    }
  }

  dynamic "forward_policy" {
    for_each = var.forward_policy
    content {
      acos_event_log       = forward_policy.value["acos_event_log"]
      local_logging        = forward_policy.value["local_logging"]
      no_client_conn_reuse = forward_policy.value["no_client_conn_reuse"]
      require_web_category = forward_policy.value["require_web_category"]
      uuid                 = forward_policy.value["uuid"]

      dynamic "action_list" {
        for_each = forward_policy.value.action_list
        content {
          action1            = action_list.value["action1"]
          drop_message       = action_list.value["drop_message"]
          drop_redirect_url  = action_list.value["drop_redirect_url"]
          drop_response_code = action_list.value["drop_response_code"]
          fake_sg            = action_list.value["fake_sg"]
          fall_back          = action_list.value["fall_back"]
          fall_back_snat     = action_list.value["fall_back_snat"]
          forward_snat       = action_list.value["forward_snat"]
          http_status_code   = action_list.value["http_status_code"]
          log                = action_list.value["log"]
          name               = action_list.value["name"]
          real_sg            = action_list.value["real_sg"]
          user_tag           = action_list.value["user_tag"]
          uuid               = action_list.value["uuid"]

          dynamic "sampling_enable" {
            for_each = action_list.value.sampling_enable
            content {
              counters1 = sampling_enable.value["counters1"]
            }
          }

        }
      }

      dynamic "filtering" {
        for_each = forward_policy.value.filtering
        content {
          ssli_url_filtering = filtering.value["ssli_url_filtering"]
        }
      }

      dynamic "san_filtering" {
        for_each = forward_policy.value.san_filtering
        content {
          ssli_url_filtering_san = san_filtering.value["ssli_url_filtering_san"]
        }
      }

      dynamic "source_list" {
        for_each = forward_policy.value.source_list
        content {
          match_any              = source_list.value["match_any"]
          match_authorize_policy = source_list.value["match_authorize_policy"]
          match_class_list       = source_list.value["match_class_list"]
          name                   = source_list.value["name"]
          priority               = source_list.value["priority"]
          user_tag               = source_list.value["user_tag"]
          uuid                   = source_list.value["uuid"]

          dynamic "destination" {
            for_each = source_list.value.destination
            content {

              dynamic "any" {
                for_each = destination.value.any
                content {
                  action = any.value["action"]
                  uuid   = any.value["uuid"]

                  dynamic "sampling_enable" {
                    for_each = any.value.sampling_enable
                    content {
                      counters1 = sampling_enable.value["counters1"]
                    }
                  }

                }
              }

              dynamic "class_list_list" {
                for_each = destination.value.class_list_list
                content {
                  action          = class_list_list.value["action"]
                  dest_class_list = class_list_list.value["dest_class_list"]
                  priority        = class_list_list.value["priority"]
                  type            = class_list_list.value["type"]
                  uuid            = class_list_list.value["uuid"]

                  dynamic "sampling_enable" {
                    for_each = class_list_list.value.sampling_enable
                    content {
                      counters1 = sampling_enable.value["counters1"]
                    }
                  }

                }
              }

              dynamic "web_category_list_list" {
                for_each = destination.value.web_category_list_list
                content {
                  action            = web_category_list_list.value["action"]
                  priority          = web_category_list_list.value["priority"]
                  type              = web_category_list_list.value["type"]
                  uuid              = web_category_list_list.value["uuid"]
                  web_category_list = web_category_list_list.value["web_category_list"]

                  dynamic "sampling_enable" {
                    for_each = web_category_list_list.value.sampling_enable
                    content {
                      counters1 = sampling_enable.value["counters1"]
                    }
                  }

                }
              }

            }
          }

          dynamic "sampling_enable" {
            for_each = source_list.value.sampling_enable
            content {
              counters1 = sampling_enable.value["counters1"]
            }
          }

        }
      }

    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      counters1 = sampling_enable.value["counters1"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_policy.this.id
}

output "this" {
  value = thunder_slb_template_policy.this
}
```

[top](#index)