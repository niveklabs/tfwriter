# nsxt_lb_http_forwarding_rule

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
module "nsxt_lb_http_forwarding_rule" {
  source = "./modules/nsxt/r/nsxt_lb_http_forwarding_rule"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # match_strategy - (optional) is a type of string
  match_strategy = null

  body_condition = [{
    case_sensitive = null
    inverse        = null
    match_type     = null
    value          = null
  }]

  cookie_condition = [{
    case_sensitive = null
    inverse        = null
    match_type     = null
    name           = null
    value          = null
  }]

  header_condition = [{
    case_sensitive = null
    inverse        = null
    match_type     = null
    name           = null
    value          = null
  }]

  http_redirect_action = [{
    redirect_status = null
    redirect_url    = null
  }]

  http_reject_action = [{
    reply_message = null
    reply_status  = null
  }]

  ip_condition = [{
    inverse        = null
    source_address = null
  }]

  method_condition = [{
    inverse = null
    method  = null
  }]

  select_pool_action = [{
    pool_id = null
  }]

  tag = [{
    scope = null
    tag   = null
  }]

  tcp_condition = [{
    inverse     = null
    source_port = null
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

variable "body_condition" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      case_sensitive = bool
      inverse        = bool
      match_type     = string
      value          = string
    }
  ))
  default = []
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

variable "header_condition" {
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

variable "http_redirect_action" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      redirect_status = string
      redirect_url    = string
    }
  ))
  default = []
}

variable "http_reject_action" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      reply_message = string
      reply_status  = string
    }
  ))
  default = []
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

variable "select_pool_action" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      pool_id = string
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
resource "nsxt_lb_http_forwarding_rule" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # match_strategy - (optional) is a type of string
  match_strategy = var.match_strategy

  dynamic "body_condition" {
    for_each = var.body_condition
    content {
      # case_sensitive - (optional) is a type of bool
      case_sensitive = body_condition.value["case_sensitive"]
      # inverse - (optional) is a type of bool
      inverse = body_condition.value["inverse"]
      # match_type - (required) is a type of string
      match_type = body_condition.value["match_type"]
      # value - (required) is a type of string
      value = body_condition.value["value"]
    }
  }

  dynamic "cookie_condition" {
    for_each = var.cookie_condition
    content {
      # case_sensitive - (optional) is a type of bool
      case_sensitive = cookie_condition.value["case_sensitive"]
      # inverse - (optional) is a type of bool
      inverse = cookie_condition.value["inverse"]
      # match_type - (required) is a type of string
      match_type = cookie_condition.value["match_type"]
      # name - (required) is a type of string
      name = cookie_condition.value["name"]
      # value - (required) is a type of string
      value = cookie_condition.value["value"]
    }
  }

  dynamic "header_condition" {
    for_each = var.header_condition
    content {
      # case_sensitive - (optional) is a type of bool
      case_sensitive = header_condition.value["case_sensitive"]
      # inverse - (optional) is a type of bool
      inverse = header_condition.value["inverse"]
      # match_type - (required) is a type of string
      match_type = header_condition.value["match_type"]
      # name - (required) is a type of string
      name = header_condition.value["name"]
      # value - (required) is a type of string
      value = header_condition.value["value"]
    }
  }

  dynamic "http_redirect_action" {
    for_each = var.http_redirect_action
    content {
      # redirect_status - (required) is a type of string
      redirect_status = http_redirect_action.value["redirect_status"]
      # redirect_url - (required) is a type of string
      redirect_url = http_redirect_action.value["redirect_url"]
    }
  }

  dynamic "http_reject_action" {
    for_each = var.http_reject_action
    content {
      # reply_message - (required) is a type of string
      reply_message = http_reject_action.value["reply_message"]
      # reply_status - (required) is a type of string
      reply_status = http_reject_action.value["reply_status"]
    }
  }

  dynamic "ip_condition" {
    for_each = var.ip_condition
    content {
      # inverse - (optional) is a type of bool
      inverse = ip_condition.value["inverse"]
      # source_address - (required) is a type of string
      source_address = ip_condition.value["source_address"]
    }
  }

  dynamic "method_condition" {
    for_each = var.method_condition
    content {
      # inverse - (optional) is a type of bool
      inverse = method_condition.value["inverse"]
      # method - (required) is a type of string
      method = method_condition.value["method"]
    }
  }

  dynamic "select_pool_action" {
    for_each = var.select_pool_action
    content {
      # pool_id - (required) is a type of string
      pool_id = select_pool_action.value["pool_id"]
    }
  }

  dynamic "tag" {
    for_each = var.tag
    content {
      # scope - (optional) is a type of string
      scope = tag.value["scope"]
      # tag - (optional) is a type of string
      tag = tag.value["tag"]
    }
  }

  dynamic "tcp_condition" {
    for_each = var.tcp_condition
    content {
      # inverse - (optional) is a type of bool
      inverse = tcp_condition.value["inverse"]
      # source_port - (required) is a type of string
      source_port = tcp_condition.value["source_port"]
    }
  }

  dynamic "uri_condition" {
    for_each = var.uri_condition
    content {
      # case_sensitive - (optional) is a type of bool
      case_sensitive = uri_condition.value["case_sensitive"]
      # inverse - (optional) is a type of bool
      inverse = uri_condition.value["inverse"]
      # match_type - (required) is a type of string
      match_type = uri_condition.value["match_type"]
      # uri - (required) is a type of string
      uri = uri_condition.value["uri"]
    }
  }

  dynamic "version_condition" {
    for_each = var.version_condition
    content {
      # inverse - (optional) is a type of bool
      inverse = version_condition.value["inverse"]
      # version - (required) is a type of string
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
  value       = nsxt_lb_http_forwarding_rule.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_http_forwarding_rule.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_http_forwarding_rule.this.revision
}

output "this" {
  value = nsxt_lb_http_forwarding_rule.this
}
```

[top](#index)