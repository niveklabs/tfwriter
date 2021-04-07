# nsxt_lb_http_monitor

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
module "nsxt_lb_http_monitor" {
  source = "./modules/nsxt/r/nsxt_lb_http_monitor"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # fall_count - (optional) is a type of number
  fall_count = null
  # interval - (optional) is a type of number
  interval = null
  # monitor_port - (optional) is a type of string
  monitor_port = null
  # request_body - (optional) is a type of string
  request_body = null
  # request_method - (optional) is a type of string
  request_method = null
  # request_url - (optional) is a type of string
  request_url = null
  # request_version - (optional) is a type of string
  request_version = null
  # response_body - (optional) is a type of string
  response_body = null
  # response_status_codes - (optional) is a type of list of number
  response_status_codes = []
  # rise_count - (optional) is a type of number
  rise_count = null
  # timeout - (optional) is a type of number
  timeout = null

  request_header = [{
    name  = null
    value = null
  }]

  tag = [{
    scope = null
    tag   = null
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

variable "fall_count" {
  description = "(optional) - Number of consecutive checks that must fail before marking it down"
  type        = number
  default     = null
}

variable "interval" {
  description = "(optional) - The frequency at which the system issues the monitor check (in seconds)"
  type        = number
  default     = null
}

variable "monitor_port" {
  description = "(optional) - If the monitor port is specified, it would override pool member port setting for healthcheck. A port range is not supported"
  type        = string
  default     = null
}

variable "request_body" {
  description = "(optional) - String to send as HTTP health check request body. Valid only for certain HTTP methods like POST"
  type        = string
  default     = null
}

variable "request_method" {
  description = "(optional) - Health check method for HTTP monitor type"
  type        = string
  default     = null
}

variable "request_url" {
  description = "(optional) - URL used for HTTP monitor"
  type        = string
  default     = null
}

variable "request_version" {
  description = "(optional) - HTTP request version"
  type        = string
  default     = null
}

variable "response_body" {
  description = "(optional) - If HTTP specified, healthcheck HTTP response body is matched against the specified string (regular expressions not supported), and succeeds only if there is a match"
  type        = string
  default     = null
}

variable "response_status_codes" {
  description = "(optional) - The HTTP response status code should be a valid HTTP status code"
  type        = list(number)
  default     = null
}

variable "rise_count" {
  description = "(optional) - Number of consecutive checks that must pass before marking it up"
  type        = number
  default     = null
}

variable "timeout" {
  description = "(optional) - Number of seconds the target has to respond to the monitor request"
  type        = number
  default     = null
}

variable "request_header" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
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
```

[top](#index)

### Resource

```terraform
resource "nsxt_lb_http_monitor" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # fall_count - (optional) is a type of number
  fall_count = var.fall_count
  # interval - (optional) is a type of number
  interval = var.interval
  # monitor_port - (optional) is a type of string
  monitor_port = var.monitor_port
  # request_body - (optional) is a type of string
  request_body = var.request_body
  # request_method - (optional) is a type of string
  request_method = var.request_method
  # request_url - (optional) is a type of string
  request_url = var.request_url
  # request_version - (optional) is a type of string
  request_version = var.request_version
  # response_body - (optional) is a type of string
  response_body = var.response_body
  # response_status_codes - (optional) is a type of list of number
  response_status_codes = var.response_status_codes
  # rise_count - (optional) is a type of number
  rise_count = var.rise_count
  # timeout - (optional) is a type of number
  timeout = var.timeout

  dynamic "request_header" {
    for_each = var.request_header
    content {
      # name - (required) is a type of string
      name = request_header.value["name"]
      # value - (required) is a type of string
      value = request_header.value["value"]
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

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = nsxt_lb_http_monitor.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_lb_http_monitor.this.id
}

output "response_status_codes" {
  description = "returns a list of number"
  value       = nsxt_lb_http_monitor.this.response_status_codes
}

output "revision" {
  description = "returns a number"
  value       = nsxt_lb_http_monitor.this.revision
}

output "this" {
  value = nsxt_lb_http_monitor.this
}
```

[top](#index)