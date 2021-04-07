# thunder_fw_template_logging

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
module "thunder_fw_template_logging" {
  source = "./modules/thunder/r/thunder_fw_template_logging"

  # facility - (optional) is a type of string
  facility = null
  # format - (optional) is a type of string
  format = null
  # include_dest_fqdn - (optional) is a type of number
  include_dest_fqdn = null
  # merged_style - (optional) is a type of number
  merged_style = null
  # name - (optional) is a type of string
  name = null
  # resolution - (optional) is a type of string
  resolution = null
  # service_group - (optional) is a type of string
  service_group = null
  # severity - (optional) is a type of string
  severity = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  include_http = [{
    file_extension = null
    header_cfg = [{
      custom_header_name = null
      custom_max_length  = null
      http_header        = null
      max_length         = null
    }]
    l4_session_info = null
    method          = null
    request_number  = null
  }]

  include_radius_attribute = [{
    attr_cfg = [{
      attr       = null
      attr_event = null
    }]
    framed_ipv6_prefix     = null
    insert_if_not_existing = null
    no_quote               = null
    prefix_length          = null
    zero_in_custom_attr    = null
  }]

  log = [{
    http_requests = null
  }]

  rule = [{
    rule_http_requests = [{
      dest_port = [{
        dest_port_number   = null
        include_byte_count = null
      }]
      disable_sequence_check = null
      include_all_headers    = null
      log_every_http_request = null
      max_url_len            = null
    }]
  }]

  source_address = [{
    ip   = null
    ipv6 = null
    uuid = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "facility" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "include_dest_fqdn" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "merged_style" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolution" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_group" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "severity" {
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

variable "include_http" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      file_extension = number
      header_cfg = list(object(
        {
          custom_header_name = string
          custom_max_length  = number
          http_header        = string
          max_length         = number
        }
      ))
      l4_session_info = number
      method          = number
      request_number  = number
    }
  ))
  default = []
}

variable "include_radius_attribute" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      attr_cfg = list(object(
        {
          attr       = string
          attr_event = string
        }
      ))
      framed_ipv6_prefix     = number
      insert_if_not_existing = number
      no_quote               = number
      prefix_length          = string
      zero_in_custom_attr    = number
    }
  ))
  default = []
}

variable "log" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      http_requests = string
    }
  ))
  default = []
}

variable "rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      rule_http_requests = list(object(
        {
          dest_port = list(object(
            {
              dest_port_number   = number
              include_byte_count = number
            }
          ))
          disable_sequence_check = number
          include_all_headers    = number
          log_every_http_request = number
          max_url_len            = number
        }
      ))
    }
  ))
  default = []
}

variable "source_address" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ip   = string
      ipv6 = string
      uuid = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_fw_template_logging" "this" {
  # facility - (optional) is a type of string
  facility = var.facility
  # format - (optional) is a type of string
  format = var.format
  # include_dest_fqdn - (optional) is a type of number
  include_dest_fqdn = var.include_dest_fqdn
  # merged_style - (optional) is a type of number
  merged_style = var.merged_style
  # name - (optional) is a type of string
  name = var.name
  # resolution - (optional) is a type of string
  resolution = var.resolution
  # service_group - (optional) is a type of string
  service_group = var.service_group
  # severity - (optional) is a type of string
  severity = var.severity
  # user_tag - (optional) is a type of string
  user_tag = var.user_tag
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "include_http" {
    for_each = var.include_http
    content {
      # file_extension - (optional) is a type of number
      file_extension = include_http.value["file_extension"]
      # l4_session_info - (optional) is a type of number
      l4_session_info = include_http.value["l4_session_info"]
      # method - (optional) is a type of number
      method = include_http.value["method"]
      # request_number - (optional) is a type of number
      request_number = include_http.value["request_number"]

      dynamic "header_cfg" {
        for_each = include_http.value.header_cfg
        content {
          # custom_header_name - (optional) is a type of string
          custom_header_name = header_cfg.value["custom_header_name"]
          # custom_max_length - (optional) is a type of number
          custom_max_length = header_cfg.value["custom_max_length"]
          # http_header - (optional) is a type of string
          http_header = header_cfg.value["http_header"]
          # max_length - (optional) is a type of number
          max_length = header_cfg.value["max_length"]
        }
      }

    }
  }

  dynamic "include_radius_attribute" {
    for_each = var.include_radius_attribute
    content {
      # framed_ipv6_prefix - (optional) is a type of number
      framed_ipv6_prefix = include_radius_attribute.value["framed_ipv6_prefix"]
      # insert_if_not_existing - (optional) is a type of number
      insert_if_not_existing = include_radius_attribute.value["insert_if_not_existing"]
      # no_quote - (optional) is a type of number
      no_quote = include_radius_attribute.value["no_quote"]
      # prefix_length - (optional) is a type of string
      prefix_length = include_radius_attribute.value["prefix_length"]
      # zero_in_custom_attr - (optional) is a type of number
      zero_in_custom_attr = include_radius_attribute.value["zero_in_custom_attr"]

      dynamic "attr_cfg" {
        for_each = include_radius_attribute.value.attr_cfg
        content {
          # attr - (optional) is a type of string
          attr = attr_cfg.value["attr"]
          # attr_event - (optional) is a type of string
          attr_event = attr_cfg.value["attr_event"]
        }
      }

    }
  }

  dynamic "log" {
    for_each = var.log
    content {
      # http_requests - (optional) is a type of string
      http_requests = log.value["http_requests"]
    }
  }

  dynamic "rule" {
    for_each = var.rule
    content {

      dynamic "rule_http_requests" {
        for_each = rule.value.rule_http_requests
        content {
          # disable_sequence_check - (optional) is a type of number
          disable_sequence_check = rule_http_requests.value["disable_sequence_check"]
          # include_all_headers - (optional) is a type of number
          include_all_headers = rule_http_requests.value["include_all_headers"]
          # log_every_http_request - (optional) is a type of number
          log_every_http_request = rule_http_requests.value["log_every_http_request"]
          # max_url_len - (optional) is a type of number
          max_url_len = rule_http_requests.value["max_url_len"]

          dynamic "dest_port" {
            for_each = rule_http_requests.value.dest_port
            content {
              # dest_port_number - (optional) is a type of number
              dest_port_number = dest_port.value["dest_port_number"]
              # include_byte_count - (optional) is a type of number
              include_byte_count = dest_port.value["include_byte_count"]
            }
          }

        }
      }

    }
  }

  dynamic "source_address" {
    for_each = var.source_address
    content {
      # ip - (optional) is a type of string
      ip = source_address.value["ip"]
      # ipv6 - (optional) is a type of string
      ipv6 = source_address.value["ipv6"]
      # uuid - (optional) is a type of string
      uuid = source_address.value["uuid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_fw_template_logging.this.id
}

output "this" {
  value = thunder_fw_template_logging.this
}
```

[top](#index)