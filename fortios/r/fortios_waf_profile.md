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
    fortios = ">= 1.6.18"
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
  comment      = var.comment
  extended_log = var.extended_log
  external     = var.external
  name         = var.name

  dynamic "address_list" {
    for_each = var.address_list
    content {
      blocked_log = address_list.value["blocked_log"]
      severity    = address_list.value["severity"]
      status      = address_list.value["status"]

      dynamic "blocked_address" {
        for_each = address_list.value.blocked_address
        content {
          name = blocked_address.value["name"]
        }
      }

      dynamic "trusted_address" {
        for_each = address_list.value.trusted_address
        content {
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
          action   = content_length.value["action"]
          length   = content_length.value["length"]
          log      = content_length.value["log"]
          severity = content_length.value["severity"]
          status   = content_length.value["status"]
        }
      }

      dynamic "exception" {
        for_each = constraint.value.exception
        content {
          address           = exception.value["address"]
          content_length    = exception.value["content_length"]
          header_length     = exception.value["header_length"]
          hostname          = exception.value["hostname"]
          id                = exception.value["id"]
          line_length       = exception.value["line_length"]
          malformed         = exception.value["malformed"]
          max_cookie        = exception.value["max_cookie"]
          max_header_line   = exception.value["max_header_line"]
          max_range_segment = exception.value["max_range_segment"]
          max_url_param     = exception.value["max_url_param"]
          method            = exception.value["method"]
          param_length      = exception.value["param_length"]
          pattern           = exception.value["pattern"]
          regex             = exception.value["regex"]
          url_param_length  = exception.value["url_param_length"]
          version           = exception.value["version"]
        }
      }

      dynamic "header_length" {
        for_each = constraint.value.header_length
        content {
          action   = header_length.value["action"]
          length   = header_length.value["length"]
          log      = header_length.value["log"]
          severity = header_length.value["severity"]
          status   = header_length.value["status"]
        }
      }

      dynamic "hostname" {
        for_each = constraint.value.hostname
        content {
          action   = hostname.value["action"]
          log      = hostname.value["log"]
          severity = hostname.value["severity"]
          status   = hostname.value["status"]
        }
      }

      dynamic "line_length" {
        for_each = constraint.value.line_length
        content {
          action   = line_length.value["action"]
          length   = line_length.value["length"]
          log      = line_length.value["log"]
          severity = line_length.value["severity"]
          status   = line_length.value["status"]
        }
      }

      dynamic "malformed" {
        for_each = constraint.value.malformed
        content {
          action   = malformed.value["action"]
          log      = malformed.value["log"]
          severity = malformed.value["severity"]
          status   = malformed.value["status"]
        }
      }

      dynamic "max_cookie" {
        for_each = constraint.value.max_cookie
        content {
          action     = max_cookie.value["action"]
          log        = max_cookie.value["log"]
          max_cookie = max_cookie.value["max_cookie"]
          severity   = max_cookie.value["severity"]
          status     = max_cookie.value["status"]
        }
      }

      dynamic "max_header_line" {
        for_each = constraint.value.max_header_line
        content {
          action          = max_header_line.value["action"]
          log             = max_header_line.value["log"]
          max_header_line = max_header_line.value["max_header_line"]
          severity        = max_header_line.value["severity"]
          status          = max_header_line.value["status"]
        }
      }

      dynamic "max_range_segment" {
        for_each = constraint.value.max_range_segment
        content {
          action            = max_range_segment.value["action"]
          log               = max_range_segment.value["log"]
          max_range_segment = max_range_segment.value["max_range_segment"]
          severity          = max_range_segment.value["severity"]
          status            = max_range_segment.value["status"]
        }
      }

      dynamic "max_url_param" {
        for_each = constraint.value.max_url_param
        content {
          action        = max_url_param.value["action"]
          log           = max_url_param.value["log"]
          max_url_param = max_url_param.value["max_url_param"]
          severity      = max_url_param.value["severity"]
          status        = max_url_param.value["status"]
        }
      }

      dynamic "method" {
        for_each = constraint.value.method
        content {
          action   = method.value["action"]
          log      = method.value["log"]
          severity = method.value["severity"]
          status   = method.value["status"]
        }
      }

      dynamic "param_length" {
        for_each = constraint.value.param_length
        content {
          action   = param_length.value["action"]
          length   = param_length.value["length"]
          log      = param_length.value["log"]
          severity = param_length.value["severity"]
          status   = param_length.value["status"]
        }
      }

      dynamic "url_param_length" {
        for_each = constraint.value.url_param_length
        content {
          action   = url_param_length.value["action"]
          length   = url_param_length.value["length"]
          log      = url_param_length.value["log"]
          severity = url_param_length.value["severity"]
          status   = url_param_length.value["status"]
        }
      }

      dynamic "version" {
        for_each = constraint.value.version
        content {
          action   = version.value["action"]
          log      = version.value["log"]
          severity = version.value["severity"]
          status   = version.value["status"]
        }
      }

    }
  }

  dynamic "method" {
    for_each = var.method
    content {
      default_allowed_methods = method.value["default_allowed_methods"]
      log                     = method.value["log"]
      severity                = method.value["severity"]
      status                  = method.value["status"]

      dynamic "method_policy" {
        for_each = method.value.method_policy
        content {
          address         = method_policy.value["address"]
          allowed_methods = method_policy.value["allowed_methods"]
          id              = method_policy.value["id"]
          pattern         = method_policy.value["pattern"]
          regex           = method_policy.value["regex"]
        }
      }

    }
  }

  dynamic "signature" {
    for_each = var.signature
    content {
      credit_card_detection_threshold = signature.value["credit_card_detection_threshold"]

      dynamic "custom_signature" {
        for_each = signature.value.custom_signature
        content {
          action           = custom_signature.value["action"]
          case_sensitivity = custom_signature.value["case_sensitivity"]
          direction        = custom_signature.value["direction"]
          log              = custom_signature.value["log"]
          name             = custom_signature.value["name"]
          pattern          = custom_signature.value["pattern"]
          severity         = custom_signature.value["severity"]
          status           = custom_signature.value["status"]
          target           = custom_signature.value["target"]
        }
      }

      dynamic "disabled_signature" {
        for_each = signature.value.disabled_signature
        content {
          id = disabled_signature.value["id"]
        }
      }

      dynamic "disabled_sub_class" {
        for_each = signature.value.disabled_sub_class
        content {
          id = disabled_sub_class.value["id"]
        }
      }

      dynamic "main_class" {
        for_each = signature.value.main_class
        content {
          action   = main_class.value["action"]
          id       = main_class.value["id"]
          log      = main_class.value["log"]
          severity = main_class.value["severity"]
          status   = main_class.value["status"]
        }
      }

    }
  }

  dynamic "url_access" {
    for_each = var.url_access
    content {
      action   = url_access.value["action"]
      address  = url_access.value["address"]
      id       = url_access.value["id"]
      log      = url_access.value["log"]
      severity = url_access.value["severity"]

      dynamic "access_pattern" {
        for_each = url_access.value.access_pattern
        content {
          id      = access_pattern.value["id"]
          negate  = access_pattern.value["negate"]
          pattern = access_pattern.value["pattern"]
          regex   = access_pattern.value["regex"]
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