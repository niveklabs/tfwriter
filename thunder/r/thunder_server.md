# thunder_server

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
module "thunder_server" {
  source = "./modules/thunder/r/thunder_server"

  # action - (optional) is a type of string
  action = null
  # conn_limit - (optional) is a type of number
  conn_limit = null
  # conn_resume - (optional) is a type of number
  conn_resume = null
  # extended_stats - (optional) is a type of number
  extended_stats = null
  # external_ip - (optional) is a type of string
  external_ip = null
  # fqdn_name - (optional) is a type of string
  fqdn_name = null
  # health_check - (optional) is a type of string
  health_check = null
  # health_check_disable - (optional) is a type of number
  health_check_disable = null
  # health_check_shared - (optional) is a type of string
  health_check_shared = null
  # host - (optional) is a type of string
  host = null
  # ipv6 - (optional) is a type of string
  ipv6 = null
  # name - (optional) is a type of string
  name = null
  # no_logging - (optional) is a type of number
  no_logging = null
  # resolve_as - (optional) is a type of string
  resolve_as = null
  # server_ipv6_addr - (optional) is a type of string
  server_ipv6_addr = null
  # shared_partition_health_check - (optional) is a type of number
  shared_partition_health_check = null
  # slow_start - (optional) is a type of number
  slow_start = null
  # spoofing_cache - (optional) is a type of number
  spoofing_cache = null
  # stats_data_action - (optional) is a type of string
  stats_data_action = null
  # template_server - (optional) is a type of string
  template_server = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
  # weight - (optional) is a type of number
  weight = null

  alternate_server = [{
    alternate      = null
    alternate_name = null
  }]

  port_list = [{
    action = null
    alternate_port = [{
      alternate             = null
      alternate_name        = null
      alternate_server_port = null
    }]
    conn_limit                = null
    conn_resume               = null
    extended_stats            = null
    follow_port_protocol      = null
    health_check              = null
    health_check_disable      = null
    health_check_follow_port  = null
    no_logging                = null
    no_ssl                    = null
    port_number               = null
    protocol                  = null
    range                     = null
    rport_health_check_shared = null
    sampling_enable = [{
      counters1 = null
    }]
    shared_rport_health_check = null
    stats_data_action         = null
    support_http2             = null
    template_port             = null
    template_server_ssl       = null
    user_tag                  = null
    uuid                      = null
    weight                    = null
  }]

  sampling_enable = [{
    counters1 = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "conn_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "conn_resume" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "extended_stats" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "external_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fqdn_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check_disable" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "health_check_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "no_logging" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resolve_as" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server_ipv6_addr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shared_partition_health_check" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "slow_start" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spoofing_cache" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stats_data_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_server" {
  description = "(optional)"
  type        = string
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

variable "weight" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "alternate_server" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      alternate      = number
      alternate_name = string
    }
  ))
  default = []
}

variable "port_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action = string
      alternate_port = list(object(
        {
          alternate             = number
          alternate_name        = string
          alternate_server_port = number
        }
      ))
      conn_limit                = number
      conn_resume               = number
      extended_stats            = number
      follow_port_protocol      = string
      health_check              = string
      health_check_disable      = number
      health_check_follow_port  = number
      no_logging                = number
      no_ssl                    = number
      port_number               = number
      protocol                  = string
      range                     = number
      rport_health_check_shared = string
      sampling_enable = list(object(
        {
          counters1 = string
        }
      ))
      shared_rport_health_check = number
      stats_data_action         = string
      support_http2             = number
      template_port             = string
      template_server_ssl       = string
      user_tag                  = string
      uuid                      = string
      weight                    = number
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
resource "thunder_server" "this" {
  # action - (optional) is a type of string
  action = var.action
  # conn_limit - (optional) is a type of number
  conn_limit = var.conn_limit
  # conn_resume - (optional) is a type of number
  conn_resume = var.conn_resume
  # extended_stats - (optional) is a type of number
  extended_stats = var.extended_stats
  # external_ip - (optional) is a type of string
  external_ip = var.external_ip
  # fqdn_name - (optional) is a type of string
  fqdn_name = var.fqdn_name
  # health_check - (optional) is a type of string
  health_check = var.health_check
  # health_check_disable - (optional) is a type of number
  health_check_disable = var.health_check_disable
  # health_check_shared - (optional) is a type of string
  health_check_shared = var.health_check_shared
  # host - (optional) is a type of string
  host = var.host
  # ipv6 - (optional) is a type of string
  ipv6 = var.ipv6
  # name - (optional) is a type of string
  name = var.name
  # no_logging - (optional) is a type of number
  no_logging = var.no_logging
  # resolve_as - (optional) is a type of string
  resolve_as = var.resolve_as
  # server_ipv6_addr - (optional) is a type of string
  server_ipv6_addr = var.server_ipv6_addr
  # shared_partition_health_check - (optional) is a type of number
  shared_partition_health_check = var.shared_partition_health_check
  # slow_start - (optional) is a type of number
  slow_start = var.slow_start
  # spoofing_cache - (optional) is a type of number
  spoofing_cache = var.spoofing_cache
  # stats_data_action - (optional) is a type of string
  stats_data_action = var.stats_data_action
  # template_server - (optional) is a type of string
  template_server = var.template_server
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # weight - (optional) is a type of number
  weight = var.weight

  dynamic "alternate_server" {
    for_each = var.alternate_server
    content {
      # alternate - (optional) is a type of number
      alternate = alternate_server.value["alternate"]
      # alternate_name - (optional) is a type of string
      alternate_name = alternate_server.value["alternate_name"]
    }
  }

  dynamic "port_list" {
    for_each = var.port_list
    content {
      # action - (optional) is a type of string
      action = port_list.value["action"]
      # conn_limit - (optional) is a type of number
      conn_limit = port_list.value["conn_limit"]
      # conn_resume - (optional) is a type of number
      conn_resume = port_list.value["conn_resume"]
      # extended_stats - (optional) is a type of number
      extended_stats = port_list.value["extended_stats"]
      # follow_port_protocol - (optional) is a type of string
      follow_port_protocol = port_list.value["follow_port_protocol"]
      # health_check - (optional) is a type of string
      health_check = port_list.value["health_check"]
      # health_check_disable - (optional) is a type of number
      health_check_disable = port_list.value["health_check_disable"]
      # health_check_follow_port - (optional) is a type of number
      health_check_follow_port = port_list.value["health_check_follow_port"]
      # no_logging - (optional) is a type of number
      no_logging = port_list.value["no_logging"]
      # no_ssl - (optional) is a type of number
      no_ssl = port_list.value["no_ssl"]
      # port_number - (optional) is a type of number
      port_number = port_list.value["port_number"]
      # protocol - (optional) is a type of string
      protocol = port_list.value["protocol"]
      # range - (optional) is a type of number
      range = port_list.value["range"]
      # rport_health_check_shared - (optional) is a type of string
      rport_health_check_shared = port_list.value["rport_health_check_shared"]
      # shared_rport_health_check - (optional) is a type of number
      shared_rport_health_check = port_list.value["shared_rport_health_check"]
      # stats_data_action - (optional) is a type of string
      stats_data_action = port_list.value["stats_data_action"]
      # support_http2 - (optional) is a type of number
      support_http2 = port_list.value["support_http2"]
      # template_port - (optional) is a type of string
      template_port = port_list.value["template_port"]
      # template_server_ssl - (optional) is a type of string
      template_server_ssl = port_list.value["template_server_ssl"]
      # user_tag - (optional) is a type of string
      user_tag = port_list.value["user_tag"]
      # uuid - (optional) is a type of string
      uuid = port_list.value["uuid"]
      # weight - (optional) is a type of number
      weight = port_list.value["weight"]

      dynamic "alternate_port" {
        for_each = port_list.value.alternate_port
        content {
          # alternate - (optional) is a type of number
          alternate = alternate_port.value["alternate"]
          # alternate_name - (optional) is a type of string
          alternate_name = alternate_port.value["alternate_name"]
          # alternate_server_port - (optional) is a type of number
          alternate_server_port = alternate_port.value["alternate_server_port"]
        }
      }

      dynamic "sampling_enable" {
        for_each = port_list.value.sampling_enable
        content {
          # counters1 - (optional) is a type of string
          counters1 = sampling_enable.value["counters1"]
        }
      }

    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      # counters1 - (optional) is a type of string
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
  value       = thunder_server.this.id
}

output "this" {
  value = thunder_server.this
}
```

[top](#index)