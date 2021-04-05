# thunder_slb_template_dns

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
module "thunder_slb_template_dns" {
  source = "./modules/thunder/r/thunder_slb_template_dns"

  # default_policy - (optional) is a type of string
  default_policy = null
  # disable_dns_template - (optional) is a type of number
  disable_dns_template = null
  # dnssec_service_group - (optional) is a type of string
  dnssec_service_group = null
  # drop - (optional) is a type of number
  drop = null
  # enable_cache_sharing - (optional) is a type of number
  enable_cache_sharing = null
  # forward - (optional) is a type of string
  forward = null
  # max_cache_entry_size - (optional) is a type of number
  max_cache_entry_size = null
  # max_cache_size - (optional) is a type of number
  max_cache_size = null
  # max_query_length - (optional) is a type of number
  max_query_length = null
  # name - (optional) is a type of string
  name = null
  # period - (optional) is a type of number
  period = null
  # query_id_switch - (optional) is a type of number
  query_id_switch = null
  # redirect_to_tcp_port - (optional) is a type of number
  redirect_to_tcp_port = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  class_list = [{
    lid_list = [{
      action_value      = null
      conn_rate_limit   = null
      lidnum            = null
      lockout           = null
      log               = null
      log_interval      = null
      over_limit_action = null
      per               = null
      user_tag          = null
      uuid              = null
    }]
    name = null
    uuid = null
  }]

  response_rate_limiting = [{
    action               = null
    enable_log           = null
    filter_response_rate = null
    response_rate        = null
    slip_rate            = null
    uuid                 = null
    window               = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disable_dns_template" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "dnssec_service_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "drop" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_cache_sharing" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "forward" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "max_cache_entry_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_cache_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_query_length" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "query_id_switch" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "redirect_to_tcp_port" {
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

variable "class_list" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      lid_list = list(object(
        {
          action_value      = string
          conn_rate_limit   = number
          lidnum            = number
          lockout           = number
          log               = number
          log_interval      = number
          over_limit_action = number
          per               = number
          user_tag          = string
          uuid              = string
        }
      ))
      name = string
      uuid = string
    }
  ))
  default = []
}

variable "response_rate_limiting" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      action               = string
      enable_log           = number
      filter_response_rate = number
      response_rate        = number
      slip_rate            = number
      uuid                 = string
      window               = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_slb_template_dns" "this" {
  default_policy       = var.default_policy
  disable_dns_template = var.disable_dns_template
  dnssec_service_group = var.dnssec_service_group
  drop                 = var.drop
  enable_cache_sharing = var.enable_cache_sharing
  forward              = var.forward
  max_cache_entry_size = var.max_cache_entry_size
  max_cache_size       = var.max_cache_size
  max_query_length     = var.max_query_length
  name                 = var.name
  period               = var.period
  query_id_switch      = var.query_id_switch
  redirect_to_tcp_port = var.redirect_to_tcp_port
  user_tag             = var.user_tag
  uuid                 = var.uuid

  dynamic "class_list" {
    for_each = var.class_list
    content {
      name = class_list.value["name"]
      uuid = class_list.value["uuid"]

      dynamic "lid_list" {
        for_each = class_list.value.lid_list
        content {
          action_value      = lid_list.value["action_value"]
          conn_rate_limit   = lid_list.value["conn_rate_limit"]
          lidnum            = lid_list.value["lidnum"]
          lockout           = lid_list.value["lockout"]
          log               = lid_list.value["log"]
          log_interval      = lid_list.value["log_interval"]
          over_limit_action = lid_list.value["over_limit_action"]
          per               = lid_list.value["per"]
          user_tag          = lid_list.value["user_tag"]
          uuid              = lid_list.value["uuid"]
        }
      }

    }
  }

  dynamic "response_rate_limiting" {
    for_each = var.response_rate_limiting
    content {
      action               = response_rate_limiting.value["action"]
      enable_log           = response_rate_limiting.value["enable_log"]
      filter_response_rate = response_rate_limiting.value["filter_response_rate"]
      response_rate        = response_rate_limiting.value["response_rate"]
      slip_rate            = response_rate_limiting.value["slip_rate"]
      uuid                 = response_rate_limiting.value["uuid"]
      window               = response_rate_limiting.value["window"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_slb_template_dns.this.id
}

output "this" {
  value = thunder_slb_template_dns.this
}
```

[top](#index)