# fortios_waf_profile

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_waf_profile" {
  source = "./modules/fortios/r/fortios_waf_profile"

  # comment - (optional) is a type of string
  comment = null
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = null
  # extended_log - (optional) is a type of string
  extended_log = null
  # external - (optional) is a type of string
  external = null
  # name - (optional) is a type of string
  name = null

  address_list = [{
    blocked_address = [{
      name = null
    }]
    blocked_log = null
    severity    = null
    status      = null
    trusted_address = [{
      name = null
    }]
  }]

  constraint = [{
    content_length = [{
      action   = null
      length   = null
      log      = null
      severity = null
      status   = null
    }]
    exception = [{
      address           = null
      content_length    = null
      header_length     = null
      hostname          = null
      id                = null
      line_length       = null
      malformed         = null
      max_cookie        = null
      max_header_line   = null
      max_range_segment = null
      max_url_param     = null
      method            = null
      param_length      = null
      pattern           = null
      regex             = null
      url_param_length  = null
      version           = null
    }]
    header_length = [{
      action   = null
      length   = null
      log      = null
      severity = null
      status   = null
    }]
    hostname = [{
      action   = null
      log      = null
      severity = null
      status   = null
    }]
    line_length = [{
      action   = null
      length   = null
      log      = null
      severity = null
      status   = null
    }]
    malformed = [{
      action   = null
      log      = null
      severity = null
      status   = null
    }]
    max_cookie = [{
      action     = null
      log        = null
      max_cookie = null
      severity   = null
      status     = null
    }]
    max_header_line = [{
      action          = null
      log             = null
      max_header_line = null
      severity        = null
      status          = null
    }]
    max_range_segment = [{
      action            = null
      log               = null
      max_range_segment = null
      severity          = null
      status            = null
    }]
    max_url_param = [{
      action        = null
      log           = null
      max_url_param = null
      severity      = null
      status        = null
    }]
    method = [{
      action   = null
      log      = null
      severity = null
      status   = null
    }]
    param_length = [{
      action   = null
      length   = null
      log      = null
      severity = null
      status   = null
    }]
    url_param_length = [{
      action   = null
      length   = null
      log      = null
      severity = null
      status   = null
    }]
    version = [{
      action   = null
      log      = null
      severity = null
      status   = null
    }]
  }]

  method = [{
    default_allowed_methods = null
    log                     = null
    method_policy = [{
      address         = null
      allowed_methods = null
      id              = null
      pattern         = null
      regex           = null
    }]
    severity = null
    status   = null
  }]

  signature = [{
    credit_card_detection_threshold = null
    custom_signature = [{
      action           = null
      case_sensitivity = null
      direction        = null
      log              = null
      name             = null
      pattern          = null
      severity         = null
      status           = null
      target           = null
    }]
    disabled_signature = [{
      id = null
    }]
    disabled_sub_class = [{
      id = null
    }]
    main_class = [{
      action   = null
      id       = null
      log      = null
      severity = null
      status   = null
    }]
  }]

  url_access = [{
    access_pattern = [{
      id      = null
      negate  = null
      pattern = null
      regex   = null
      srcaddr = null
    }]
    action   = null
    address  = null
    id       = null
    log      = null
    severity = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dynamic_sort_subtable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "extended_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "external" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "address_list" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      blocked_address = list(object(
        {
          name = string
        }
      ))
      blocked_log = string
      severity    = string
      status      = string
      trusted_address = list(object(
        {
          name = string
        }
      ))
    }
  ))
  default = []
}

variable "constraint" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      content_length = list(object(
        {
          action   = string
          length   = number
          log      = string
          severity = string
          status   = string
        }
      ))
      exception = list(object(
        {
          address           = string
          content_length    = string
          header_length     = string
          hostname          = string
          id                = number
          line_length       = string
          malformed         = string
          max_cookie        = string
          max_header_line   = string
          max_range_segment = string
          max_url_param     = string
          method            = string
          param_length      = string
          pattern           = string
          regex             = string
          url_param_length  = string
          version           = string
        }
      ))
      header_length = list(object(
        {
          action   = string
          length   = number
          log      = string
          severity = string
          status   = string
        }
      ))
      hostname = list(object(
        {
          action   = string
          log      = string
          severity = string
          status   = string
        }
      ))
      line_length = list(object(
        {
          action   = string
          length   = number
          log      = string
          severity = string
          status   = string
        }
      ))
      malformed = list(object(
        {
          action   = string
          log      = string
          severity = string
          status   = string
        }
      ))
      max_cookie = list(object(
        {
          action     = string
          log        = string
          max_cookie = number
          severity   = string
          status     = string
        }
      ))
      max_header_line = list(object(
        {
          action          = string
          log             = string
          max_header_line = number
          severity        = string
          status          = string
        }
      ))
      max_range_segment = list(object(
        {
          action            = string
          log               = string
          max_range_segment = number
          severity          = string
          status            = string
        }
      ))
      max_url_param = list(object(
        {
          action        = string
          log           = string
          max_url_param = number
          severity      = string
          status        = string
        }
      ))
      method = list(object(
        {
          action   = string
          log      = string
          severity = string
          status   = string
        }
      ))
      param_length = list(object(
        {
          action   = string
          length   = number
          log      = string
          severity = string
          status   = string
        }
      ))
      url_param_length = list(object(
        {
          action   = string
          length   = number
          log      = string
          severity = string
          status   = string
        }
      ))
      version = list(object(
        {
          action   = string
          log      = string
          severity = string
          status   = string
        }
      ))
    }
  ))
  default = []
}

variable "method" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default_allowed_methods = string
      log                     = string
      method_policy = list(object(
        {
          address         = string
          allowed_methods = string
          id              = number
          pattern         = string
          regex           = string
        }
      ))
      severity = string
      status   = string
    }
  ))
  default = []
}

variable "signature" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      credit_card_detection_threshold = number
      custom_signature = list(object(
        {
          action           = string
          case_sensitivity = string
          direction        = string
          log              = string
          name             = string
          pattern          = string
          severity         = string
          status           = string
          target           = string
        }
      ))
      disabled_signature = list(object(
        {
          id = number
        }
      ))
      disabled_sub_class = list(object(
        {
          id = number
        }
      ))
      main_class = list(object(
        {
          action   = string
          id       = number
          log      = string
          severity = string
          status   = string
        }
      ))
    }
  ))
  default = []
}

variable "url_access" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_pattern = list(object(
        {
          id      = number
          negate  = string
          pattern = string
          regex   = string
          srcaddr = string
        }
      ))
      action   = string
      address  = string
      id       = number
      log      = string
      severity = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "fortios_waf_profile" "this" {
  # comment - (optional) is a type of string
  comment = var.comment
  # dynamic_sort_subtable - (optional) is a type of string
  dynamic_sort_subtable = var.dynamic_sort_subtable
  # extended_log - (optional) is a type of string
  extended_log = var.extended_log
  # external - (optional) is a type of string
  external = var.external
  # name - (optional) is a type of string
  name = var.name

  dynamic "address_list" {
    for_each = var.address_list
    content {
      # blocked_log - (optional) is a type of string
      blocked_log = address_list.value["blocked_log"]
      # severity - (optional) is a type of string
      severity = address_list.value["severity"]
      # status - (optional) is a type of string
      status = address_list.value["status"]

      dynamic "blocked_address" {
        for_each = address_list.value.blocked_address
        content {
          # name - (optional) is a type of string
          name = blocked_address.value["name"]
        }
      }

      dynamic "trusted_address" {
        for_each = address_list.value.trusted_address
        content {
          # name - (optional) is a type of string
          name = trusted_address.value["name"]
        }
      }

    }
  }

  dynamic "constraint" {
    for_each = var.constraint
    content {

      dynamic "content_length" {
        for_each = constraint.value.content_length
        content {
          # action - (optional) is a type of string
          action = content_length.value["action"]
          # length - (optional) is a type of number
          length = content_length.value["length"]
          # log - (optional) is a type of string
          log = content_length.value["log"]
          # severity - (optional) is a type of string
          severity = content_length.value["severity"]
          # status - (optional) is a type of string
          status = content_length.value["status"]
        }
      }

      dynamic "exception" {
        for_each = constraint.value.exception
        content {
          # address - (optional) is a type of string
          address = exception.value["address"]
          # content_length - (optional) is a type of string
          content_length = exception.value["content_length"]
          # header_length - (optional) is a type of string
          header_length = exception.value["header_length"]
          # hostname - (optional) is a type of string
          hostname = exception.value["hostname"]
          # id - (optional) is a type of number
          id = exception.value["id"]
          # line_length - (optional) is a type of string
          line_length = exception.value["line_length"]
          # malformed - (optional) is a type of string
          malformed = exception.value["malformed"]
          # max_cookie - (optional) is a type of string
          max_cookie = exception.value["max_cookie"]
          # max_header_line - (optional) is a type of string
          max_header_line = exception.value["max_header_line"]
          # max_range_segment - (optional) is a type of string
          max_range_segment = exception.value["max_range_segment"]
          # max_url_param - (optional) is a type of string
          max_url_param = exception.value["max_url_param"]
          # method - (optional) is a type of string
          method = exception.value["method"]
          # param_length - (optional) is a type of string
          param_length = exception.value["param_length"]
          # pattern - (optional) is a type of string
          pattern = exception.value["pattern"]
          # regex - (optional) is a type of string
          regex = exception.value["regex"]
          # url_param_length - (optional) is a type of string
          url_param_length = exception.value["url_param_length"]
          # version - (optional) is a type of string
          version = exception.value["version"]
        }
      }

      dynamic "header_length" {
        for_each = constraint.value.header_length
        content {
          # action - (optional) is a type of string
          action = header_length.value["action"]
          # length - (optional) is a type of number
          length = header_length.value["length"]
          # log - (optional) is a type of string
          log = header_length.value["log"]
          # severity - (optional) is a type of string
          severity = header_length.value["severity"]
          # status - (optional) is a type of string
          status = header_length.value["status"]
        }
      }

      dynamic "hostname" {
        for_each = constraint.value.hostname
        content {
          # action - (optional) is a type of string
          action = hostname.value["action"]
          # log - (optional) is a type of string
          log = hostname.value["log"]
          # severity - (optional) is a type of string
          severity = hostname.value["severity"]
          # status - (optional) is a type of string
          status = hostname.value["status"]
        }
      }

      dynamic "line_length" {
        for_each = constraint.value.line_length
        content {
          # action - (optional) is a type of string
          action = line_length.value["action"]
          # length - (optional) is a type of number
          length = line_length.value["length"]
          # log - (optional) is a type of string
          log = line_length.value["log"]
          # severity - (optional) is a type of string
          severity = line_length.value["severity"]
          # status - (optional) is a type of string
          status = line_length.value["status"]
        }
      }

      dynamic "malformed" {
        for_each = constraint.value.malformed
        content {
          # action - (optional) is a type of string
          action = malformed.value["action"]
          # log - (optional) is a type of string
          log = malformed.value["log"]
          # severity - (optional) is a type of string
          severity = malformed.value["severity"]
          # status - (optional) is a type of string
          status = malformed.value["status"]
        }
      }

      dynamic "max_cookie" {
        for_each = constraint.value.max_cookie
        content {
          # action - (optional) is a type of string
          action = max_cookie.value["action"]
          # log - (optional) is a type of string
          log = max_cookie.value["log"]
          # max_cookie - (optional) is a type of number
          max_cookie = max_cookie.value["max_cookie"]
          # severity - (optional) is a type of string
          severity = max_cookie.value["severity"]
          # status - (optional) is a type of string
          status = max_cookie.value["status"]
        }
      }

      dynamic "max_header_line" {
        for_each = constraint.value.max_header_line
        content {
          # action - (optional) is a type of string
          action = max_header_line.value["action"]
          # log - (optional) is a type of string
          log = max_header_line.value["log"]
          # max_header_line - (optional) is a type of number
          max_header_line = max_header_line.value["max_header_line"]
          # severity - (optional) is a type of string
          severity = max_header_line.value["severity"]
          # status - (optional) is a type of string
          status = max_header_line.value["status"]
        }
      }

      dynamic "max_range_segment" {
        for_each = constraint.value.max_range_segment
        content {
          # action - (optional) is a type of string
          action = max_range_segment.value["action"]
          # log - (optional) is a type of string
          log = max_range_segment.value["log"]
          # max_range_segment - (optional) is a type of number
          max_range_segment = max_range_segment.value["max_range_segment"]
          # severity - (optional) is a type of string
          severity = max_range_segment.value["severity"]
          # status - (optional) is a type of string
          status = max_range_segment.value["status"]
        }
      }

      dynamic "max_url_param" {
        for_each = constraint.value.max_url_param
        content {
          # action - (optional) is a type of string
          action = max_url_param.value["action"]
          # log - (optional) is a type of string
          log = max_url_param.value["log"]
          # max_url_param - (optional) is a type of number
          max_url_param = max_url_param.value["max_url_param"]
          # severity - (optional) is a type of string
          severity = max_url_param.value["severity"]
          # status - (optional) is a type of string
          status = max_url_param.value["status"]
        }
      }

      dynamic "method" {
        for_each = constraint.value.method
        content {
          # action - (optional) is a type of string
          action = method.value["action"]
          # log - (optional) is a type of string
          log = method.value["log"]
          # severity - (optional) is a type of string
          severity = method.value["severity"]
          # status - (optional) is a type of string
          status = method.value["status"]
        }
      }

      dynamic "param_length" {
        for_each = constraint.value.param_length
        content {
          # action - (optional) is a type of string
          action = param_length.value["action"]
          # length - (optional) is a type of number
          length = param_length.value["length"]
          # log - (optional) is a type of string
          log = param_length.value["log"]
          # severity - (optional) is a type of string
          severity = param_length.value["severity"]
          # status - (optional) is a type of string
          status = param_length.value["status"]
        }
      }

      dynamic "url_param_length" {
        for_each = constraint.value.url_param_length
        content {
          # action - (optional) is a type of string
          action = url_param_length.value["action"]
          # length - (optional) is a type of number
          length = url_param_length.value["length"]
          # log - (optional) is a type of string
          log = url_param_length.value["log"]
          # severity - (optional) is a type of string
          severity = url_param_length.value["severity"]
          # status - (optional) is a type of string
          status = url_param_length.value["status"]
        }
      }

      dynamic "version" {
        for_each = constraint.value.version
        content {
          # action - (optional) is a type of string
          action = version.value["action"]
          # log - (optional) is a type of string
          log = version.value["log"]
          # severity - (optional) is a type of string
          severity = version.value["severity"]
          # status - (optional) is a type of string
          status = version.value["status"]
        }
      }

    }
  }

  dynamic "method" {
    for_each = var.method
    content {
      # default_allowed_methods - (optional) is a type of string
      default_allowed_methods = method.value["default_allowed_methods"]
      # log - (optional) is a type of string
      log = method.value["log"]
      # severity - (optional) is a type of string
      severity = method.value["severity"]
      # status - (optional) is a type of string
      status = method.value["status"]

      dynamic "method_policy" {
        for_each = method.value.method_policy
        content {
          # address - (optional) is a type of string
          address = method_policy.value["address"]
          # allowed_methods - (optional) is a type of string
          allowed_methods = method_policy.value["allowed_methods"]
          # id - (optional) is a type of number
          id = method_policy.value["id"]
          # pattern - (optional) is a type of string
          pattern = method_policy.value["pattern"]
          # regex - (optional) is a type of string
          regex = method_policy.value["regex"]
        }
      }

    }
  }

  dynamic "signature" {
    for_each = var.signature
    content {
      # credit_card_detection_threshold - (optional) is a type of number
      credit_card_detection_threshold = signature.value["credit_card_detection_threshold"]

      dynamic "custom_signature" {
        for_each = signature.value.custom_signature
        content {
          # action - (optional) is a type of string
          action = custom_signature.value["action"]
          # case_sensitivity - (optional) is a type of string
          case_sensitivity = custom_signature.value["case_sensitivity"]
          # direction - (optional) is a type of string
          direction = custom_signature.value["direction"]
          # log - (optional) is a type of string
          log = custom_signature.value["log"]
          # name - (optional) is a type of string
          name = custom_signature.value["name"]
          # pattern - (optional) is a type of string
          pattern = custom_signature.value["pattern"]
          # severity - (optional) is a type of string
          severity = custom_signature.value["severity"]
          # status - (optional) is a type of string
          status = custom_signature.value["status"]
          # target - (optional) is a type of string
          target = custom_signature.value["target"]
        }
      }

      dynamic "disabled_signature" {
        for_each = signature.value.disabled_signature
        content {
          # id - (optional) is a type of number
          id = disabled_signature.value["id"]
        }
      }

      dynamic "disabled_sub_class" {
        for_each = signature.value.disabled_sub_class
        content {
          # id - (optional) is a type of number
          id = disabled_sub_class.value["id"]
        }
      }

      dynamic "main_class" {
        for_each = signature.value.main_class
        content {
          # action - (optional) is a type of string
          action = main_class.value["action"]
          # id - (optional) is a type of number
          id = main_class.value["id"]
          # log - (optional) is a type of string
          log = main_class.value["log"]
          # severity - (optional) is a type of string
          severity = main_class.value["severity"]
          # status - (optional) is a type of string
          status = main_class.value["status"]
        }
      }

    }
  }

  dynamic "url_access" {
    for_each = var.url_access
    content {
      # action - (optional) is a type of string
      action = url_access.value["action"]
      # address - (optional) is a type of string
      address = url_access.value["address"]
      # id - (optional) is a type of number
      id = url_access.value["id"]
      # log - (optional) is a type of string
      log = url_access.value["log"]
      # severity - (optional) is a type of string
      severity = url_access.value["severity"]

      dynamic "access_pattern" {
        for_each = url_access.value.access_pattern
        content {
          # id - (optional) is a type of number
          id = access_pattern.value["id"]
          # negate - (optional) is a type of string
          negate = access_pattern.value["negate"]
          # pattern - (optional) is a type of string
          pattern = access_pattern.value["pattern"]
          # regex - (optional) is a type of string
          regex = access_pattern.value["regex"]
          # srcaddr - (optional) is a type of string
          srcaddr = access_pattern.value["srcaddr"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "extended_log" {
  description = "returns a string"
  value       = fortios_waf_profile.this.extended_log
}

output "external" {
  description = "returns a string"
  value       = fortios_waf_profile.this.external
}

output "id" {
  description = "returns a string"
  value       = fortios_waf_profile.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_waf_profile.this.name
}

output "this" {
  value = fortios_waf_profile.this
}
```

[top](#index)