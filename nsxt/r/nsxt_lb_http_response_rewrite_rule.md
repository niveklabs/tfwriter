# nsxt_lb_http_response_rewrite_rule

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_lb_http_response_rewrite_rule" {
  source = "./modules/nsxt/r/nsxt_lb_http_response_rewrite_rule"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # match_strategy - (optional) is a type of string
  match_strategy = null

  cookie_condition = [{
    case_sensitive = null
    inverse        = null
    match_type     = null
    name           = null
    value          = null
  }]

  header_rewrite_action = [{
    name  = null
    value = null
  }]

  ip_condition = [{
    inverse        = null
    source_address = null
  }]

  method_condition = [{
    inverse = null
    method  = null
  }]

  request_header_condition = [{
    case_sensitive = null
    inverse        = null
    match_type     = null
    name           = null
    value          = null
  }]

  response_header_condition = [{
    case_sensitive = null
    inverse        = null
    match_type     = null
    name           = null
    value          = null
  }]

  tag = [{
    scope = null
    tag   = null
  }]

  tcp_condition = [{
    inverse     = null
    source_port = null
  }]

  uri_arguments_condition = [{
    case_sensitive = null
    inverse        = null
    match_type     = null
    uri_arguments  = null
  }]

  uri_condition = [{
    case_sensitive = null
    inverse        = null
    match_type     = null
    uri            = null
  }]

  version_condition = [{
    inverse = null
    version = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "match_strategy" {
  description = "(optional) - Strategy when multiple match conditions are specified in one rule (ANY vs ALL)"
  type        = string
  default     = null
}

variable "cookie_condition" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      case_sensitive = bool
      inverse        = bool
      match_type     = string
      name           = string
      value          = string
    }
  ))
  default = []
}

variable "header_rewrite_action" {
  description = "nested block: NestingSet, min items: 1, max items: 1"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
}

variable "ip_condition" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      inverse        = bool
      source_address = string
    }
  ))
  default = []
}

variable "method_condition" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      inverse = bool
      method  = string
    }
  ))
  default = []
}

variable "request_header_condition" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      case_sensitive = bool
      inverse        = bool
      match_type     = string
      name           = string
      value          = string
    }
  ))
  default = []
}

variable "response_header_condition" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      case_sensitive = bool
      inverse        = bool
      match_type     = string
      name           = string
      value          = string
    }
  ))
  default = []
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}

variable "tcp_condition" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      inverse     = bool
      source_port = string
    }
  ))
  default = []
}

variable "uri_arguments_condition" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      case_sensitive = bool
      inverse        = bool
      match_type     = string
      uri_arguments  = string
    }
  ))
  default = []
}

variable "uri_condition" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      case_sensitive = bool
      inverse        = bool
      match_type     = string
      uri            = string
    }
  ))
  default = []
}

variable "version_condition" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      inverse = bool
      version = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_lb_http_response_rewrite_rule" "this" {
  description    = var.description
  display_name   = var.display_name
  match_strategy = var.match_strategy

  dynamic "cookie_condition" {
    for_each = var.cookie_condition
    content {
      case_sensitive = cookie_condition.value["case_sensitive"]
      inverse        = cookie_condition.value["inverse"]
      match_type     = cookie_condition.value["match_type"]
      name           = cookie_condition.value["name"]
      value          = cookie_condition.value["value"]
    }
  }

  dynamic "header_rewrite_action" {
    for_each = var.header_rewrite_action
    content {
      name  = header_rewrite_action.value["name"]
      value = header_rewrite_action.value["value"]
    }
  }

  dynamic "ip_condition" {
    for_each = var.ip_condition
    content {
      inverse        = ip_condition.value["inverse"]
      source_address = ip_condition.value["source_address"]
    }
  }

  dynamic "method_condition" {
    for_each = var.method_condition
    content {
      inverse = method_condition.value["inverse"]
      method  = method_condition.value["method"]
    }
  }

  dynamic "request_header_condition" {
    for_each = var.request_header_condition
    content {
      case_sensitive = request_header_condition.value["case_sensitive"]
      inverse        = request_header_condition.value["inverse"]
      match_type     = request_header_condition.value["match_type"]
      name           = request_header_condition.value["name"]
      value          = request_header_condition.value["value"]
    }
  }

  dynamic "response_header_condition" {
    for_each = var.response_header_condition
    content {
      case_sensitive = response_header_condition.value["case_sensitive"]
      inverse        = response_header_condition.value["inverse"]
      match_type     = response_header_condition.value["match_type"]
      name           = response_header_condition.value["name"]
      value          = response_header_condition.value["value"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

  dynamic "tcp_condition" {
    for_each = var.tcp_condition
    content {
      inverse     = tcp_condition.value["inverse"]
      source_port = tcp_condition.value["source_port"]
    }
  }

  dynamic "uri_arguments_condition" {
    for_each = var.uri_arguments_condition
    content {
      case_sensitive = uri_arguments_condition.value["case_sensitive"]
      inverse        = uri_arguments_condition.value["inverse"]
      match_type     = uri_arguments_condition.value["match_type"]
      uri_arguments  = uri_arguments_condition.value["uri_arguments"]
    }
  }

  dynamic "uri_condition" {
    for_each = var.uri_condition
    content {
      case_sensitive = uri_condition.value["case_sensitive"]
      inverse        = uri_condition.value["inverse"]
      match_type     = uri_condition.value["match_type"]
      uri            = uri_condition.value["uri"]
    }
  }

  dynamic "version_condition" {
    for_each = var.version_condition
    content {
      inverse = version_condition.value["inverse"]
      version = version_condition.value["version"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = nsxt_lb_http_response_rewrite_rule.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_http_response_rewrite_rule.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_http_response_rewrite_rule.this.revision
}

output "this" {
  value = nsxt_lb_http_response_rewrite_rule.this
}
```

[top](#index)