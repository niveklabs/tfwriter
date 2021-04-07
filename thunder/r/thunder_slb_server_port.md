# thunder_slb_server_port

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
module "thunder_slb_server_port" {
  source = "./modules/thunder/r/thunder_slb_server_port"

  # action - (optional) is a type of string
  action = null
  # conn_limit - (optional) is a type of number
  conn_limit = null
  # conn_resume - (optional) is a type of number
  conn_resume = null
  # extended_stats - (optional) is a type of number
  extended_stats = null
  # follow_port_protocol - (optional) is a type of string
  follow_port_protocol = null
  # health_check - (optional) is a type of string
  health_check = null
  # health_check_disable - (optional) is a type of number
  health_check_disable = null
  # health_check_follow_port - (optional) is a type of number
  health_check_follow_port = null
  # name - (optional) is a type of string
  name = null
  # no_logging - (optional) is a type of number
  no_logging = null
  # no_ssl - (optional) is a type of number
  no_ssl = null
  # port_number - (optional) is a type of number
  port_number = null
  # protocol - (optional) is a type of string
  protocol = null
  # range - (optional) is a type of number
  range = null
  # rport_health_check_shared - (optional) is a type of string
  rport_health_check_shared = null
  # shared_partition_port_template - (optional) is a type of number
  shared_partition_port_template = null
  # shared_rport_health_check - (optional) is a type of number
  shared_rport_health_check = null
  # stats_data_action - (optional) is a type of string
  stats_data_action = null
  # support_http2 - (optional) is a type of number
  support_http2 = null
  # template_port - (optional) is a type of string
  template_port = null
  # template_port_shared - (optional) is a type of string
  template_port_shared = null
  # template_server_ssl - (optional) is a type of string
  template_server_ssl = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null
  # weight - (optional) is a type of number
  weight = null

  alternate_port = [{
    alternate             = null
    alternate_name        = null
    alternate_server_port = null
  }]

  auth_cfg = [{
    service_principal_name = null
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

variable "follow_port_protocol" {
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

variable "health_check_follow_port" {
  description = "(optional)"
  type        = number
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

variable "no_ssl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port_number" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "range" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rport_health_check_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shared_partition_port_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "shared_rport_health_check" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "stats_data_action" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "support_http2" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "template_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_port_shared" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_server_ssl" {
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

variable "alternate_port" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      alternate             = number
      alternate_name        = string
      alternate_server_port = number
    }
  ))
  default = []
}

variable "auth_cfg" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      service_principal_name = string
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
resource "thunder_slb_server_port" "this" {
  # action - (optional) is a type of string
  action = var.action
  # conn_limit - (optional) is a type of number
  conn_limit = var.conn_limit
  # conn_resume - (optional) is a type of number
  conn_resume = var.conn_resume
  # extended_stats - (optional) is a type of number
  extended_stats = var.extended_stats
  # follow_port_protocol - (optional) is a type of string
  follow_port_protocol = var.follow_port_protocol
  # health_check - (optional) is a type of string
  health_check = var.health_check
  # health_check_disable - (optional) is a type of number
  health_check_disable = var.health_check_disable
  # health_check_follow_port - (optional) is a type of number
  health_check_follow_port = var.health_check_follow_port
  # name - (optional) is a type of string
  name = var.name
  # no_logging - (optional) is a type of number
  no_logging = var.no_logging
  # no_ssl - (optional) is a type of number
  no_ssl = var.no_ssl
  # port_number - (optional) is a type of number
  port_number = var.port_number
  # protocol - (optional) is a type of string
  protocol = var.protocol
  # range - (optional) is a type of number
  range = var.range
  # rport_health_check_shared - (optional) is a type of string
  rport_health_check_shared = var.rport_health_check_shared
  # shared_partition_port_template - (optional) is a type of number
  shared_partition_port_template = var.shared_partition_port_template
  # shared_rport_health_check - (optional) is a type of number
  shared_rport_health_check = var.shared_rport_health_check
  # stats_data_action - (optional) is a type of string
  stats_data_action = var.stats_data_action
  # support_http2 - (optional) is a type of number
  support_http2 = var.support_http2
  # template_port - (optional) is a type of string
  template_port = var.template_port
  # template_port_shared - (optional) is a type of string
  template_port_shared = var.template_port_shared
  # template_server_ssl - (optional) is a type of string
  template_server_ssl = var.template_server_ssl
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid
  # weight - (optional) is a type of number
  weight = var.weight

  dynamic "alternate_port" {
    for_each = var.alternate_port
    content {
      # alternate - (optional) is a type of number
      alternate = alternate_port.value["alternate"]
      # alternate_name - (optional) is a type of string
      alternate_name = alternate_port.value["alternate_name"]
      # alternate_server_port - (optional) is a type of number
      alternate_server_port = alternate_port.value["alternate_server_port"]
    }
  }

  dynamic "auth_cfg" {
    for_each = var.auth_cfg
    content {
      # service_principal_name - (optional) is a type of string
      service_principal_name = auth_cfg.value["service_principal_name"]
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
  value       = thunder_slb_server_port.this.id
}

output "this" {
  value = thunder_slb_server_port.this
}
```

[top](#index)