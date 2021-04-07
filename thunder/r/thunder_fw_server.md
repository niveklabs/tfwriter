# thunder_fw_server

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
module "thunder_fw_server" {
  source = "./modules/thunder/r/thunder_fw_server"

  # action - (optional) is a type of string
  action = null
  # fqdn_name - (optional) is a type of string
  fqdn_name = null
  # health_check - (optional) is a type of string
  health_check = null
  # health_check_disable - (optional) is a type of number
  health_check_disable = null
  # host - (optional) is a type of string
  host = null
  # name - (optional) is a type of string
  name = null
  # resolve_as - (optional) is a type of string
  resolve_as = null
  # server_ipv6_addr - (optional) is a type of string
  server_ipv6_addr = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  port_list = [{
    action               = null
    health_check         = null
    health_check_disable = null
    port_number          = null
    protocol             = null
    sampling_enable = [{
      counters1 = null
    }]
    user_tag = null
    uuid     = null
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

variable "host" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
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

variable "port_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      action               = string
      health_check         = string
      health_check_disable = number
      port_number          = number
      protocol             = string
      sampling_enable = list(object(
        {
          counters1 = string
        }
      ))
      user_tag = string
      uuid     = string
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
resource "thunder_fw_server" "this" {
  # action - (optional) is a type of string
  action = var.action
  # fqdn_name - (optional) is a type of string
  fqdn_name = var.fqdn_name
  # health_check - (optional) is a type of string
  health_check = var.health_check
  # health_check_disable - (optional) is a type of number
  health_check_disable = var.health_check_disable
  # host - (optional) is a type of string
  host = var.host
  # name - (optional) is a type of string
  name = var.name
  # resolve_as - (optional) is a type of string
  resolve_as = var.resolve_as
  # server_ipv6_addr - (optional) is a type of string
  server_ipv6_addr = var.server_ipv6_addr
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "port_list" {
    for_each = var.port_list
    content {
      # action - (optional) is a type of string
      action = port_list.value["action"]
      # health_check - (optional) is a type of string
      health_check = port_list.value["health_check"]
      # health_check_disable - (optional) is a type of number
      health_check_disable = port_list.value["health_check_disable"]
      # port_number - (optional) is a type of number
      port_number = port_list.value["port_number"]
      # protocol - (optional) is a type of string
      protocol = port_list.value["protocol"]
      # user_tag - (optional) is a type of string
      user_tag = port_list.value["user_tag"]
      # uuid - (optional) is a type of string
      uuid = port_list.value["uuid"]

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
  value       = thunder_fw_server.this.id
}

output "this" {
  value = thunder_fw_server.this
}
```

[top](#index)