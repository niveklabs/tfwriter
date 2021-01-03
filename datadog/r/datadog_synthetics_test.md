# datadog_synthetics_test

[back](../datadog.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    datadog = ">= 2.18.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "datadog_synthetics_test" {
  source = "./modules/datadog/r/datadog_synthetics_test"

  # assertions - (optional) is a type of list of map of string
  assertions = [{}]
  # device_ids - (optional) is a type of list of string
  device_ids = []
  # locations - (required) is a type of list of string
  locations = []
  # message - (optional) is a type of string
  message = null
  # name - (required) is a type of string
  name = null
  # options - (optional) is a type of map of string
  options = {}
  # request - (required) is a type of map of string
  request = {}
  # request_headers - (optional) is a type of map of string
  request_headers = {}
  # request_query - (optional) is a type of map of string
  request_query = {}
  # status - (required) is a type of string
  status = null
  # subtype - (optional) is a type of string
  subtype = null
  # tags - (optional) is a type of list of string
  tags = []
  # type - (required) is a type of string
  type = null

  assertion = [{
    operator = null
    property = null
    target   = null
    targetjsonpath = [{
      jsonpath    = null
      operator    = null
      targetvalue = null
    }]
    type = null
  }]

  options_list = [{
    accept_self_signed   = null
    allow_insecure       = null
    follow_redirects     = null
    min_failure_duration = null
    min_location_failed  = null
    monitor_options = [{
      renotify_interval = null
    }]
    retry = [{
      count    = null
      interval = null
    }]
    tick_every = null
  }]

  request_basicauth = [{
    password = null
    username = null
  }]

  request_client_certificate = [{
    cert = [{
      content  = null
      filename = null
    }]
    key = [{
      content  = null
      filename = null
    }]
  }]

  step = [{
    allow_failure = null
    name          = null
    params        = null
    timeout       = null
    type          = null
  }]

  variable = [{
    example = null
    id      = null
    name    = null
    pattern = null
    type    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "assertions" {
  description = "(optional)"
  type        = list(map(string))
  default     = null
}

variable "device_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "locations" {
  description = "(required)"
  type        = list(string)
}

variable "message" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "options" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "request" {
  description = "(required)"
  type        = map(string)
}

variable "request_headers" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "request_query" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "status" {
  description = "(required)"
  type        = string
}

variable "subtype" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "assertion" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      operator = string
      property = string
      target   = string
      targetjsonpath = list(object(
        {
          jsonpath    = string
          operator    = string
          targetvalue = string
        }
      ))
      type = string
    }
  ))
  default = []
}

variable "options_list" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      accept_self_signed   = bool
      allow_insecure       = bool
      follow_redirects     = bool
      min_failure_duration = number
      min_location_failed  = number
      monitor_options = list(object(
        {
          renotify_interval = number
        }
      ))
      retry = list(object(
        {
          count    = number
          interval = number
        }
      ))
      tick_every = number
    }
  ))
  default = []
}

variable "request_basicauth" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      password = string
      username = string
    }
  ))
  default = []
}

variable "request_client_certificate" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cert = list(object(
        {
          content  = string
          filename = string
        }
      ))
      key = list(object(
        {
          content  = string
          filename = string
        }
      ))
    }
  ))
  default = []
}

variable "step" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allow_failure = bool
      name          = string
      params        = string
      timeout       = number
      type          = string
    }
  ))
  default = []
}

variable "variable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      example = string
      id      = string
      name    = string
      pattern = string
      type    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "datadog_synthetics_test" "this" {
  assertions      = var.assertions
  device_ids      = var.device_ids
  locations       = var.locations
  message         = var.message
  name            = var.name
  options         = var.options
  request         = var.request
  request_headers = var.request_headers
  request_query   = var.request_query
  status          = var.status
  subtype         = var.subtype
  tags            = var.tags
  type            = var.type

  dynamic "assertion" {
    for_each = var.assertion
    content {
      operator = assertion.value["operator"]
      property = assertion.value["property"]
      target   = assertion.value["target"]
      type     = assertion.value["type"]

      dynamic "targetjsonpath" {
        for_each = assertion.value.targetjsonpath
        content {
          jsonpath    = targetjsonpath.value["jsonpath"]
          operator    = targetjsonpath.value["operator"]
          targetvalue = targetjsonpath.value["targetvalue"]
        }
      }

    }
  }

  dynamic "options_list" {
    for_each = var.options_list
    content {
      accept_self_signed   = options_list.value["accept_self_signed"]
      allow_insecure       = options_list.value["allow_insecure"]
      follow_redirects     = options_list.value["follow_redirects"]
      min_failure_duration = options_list.value["min_failure_duration"]
      min_location_failed  = options_list.value["min_location_failed"]
      tick_every           = options_list.value["tick_every"]

      dynamic "monitor_options" {
        for_each = options_list.value.monitor_options
        content {
          renotify_interval = monitor_options.value["renotify_interval"]
        }
      }

      dynamic "retry" {
        for_each = options_list.value.retry
        content {
          count    = retry.value["count"]
          interval = retry.value["interval"]
        }
      }

    }
  }

  dynamic "request_basicauth" {
    for_each = var.request_basicauth
    content {
      password = request_basicauth.value["password"]
      username = request_basicauth.value["username"]
    }
  }

  dynamic "request_client_certificate" {
    for_each = var.request_client_certificate
    content {

      dynamic "cert" {
        for_each = request_client_certificate.value.cert
        content {
          content  = cert.value["content"]
          filename = cert.value["filename"]
        }
      }

      dynamic "key" {
        for_each = request_client_certificate.value.key
        content {
          content  = key.value["content"]
          filename = key.value["filename"]
        }
      }

    }
  }

  dynamic "step" {
    for_each = var.step
    content {
      allow_failure = step.value["allow_failure"]
      name          = step.value["name"]
      params        = step.value["params"]
      timeout       = step.value["timeout"]
      type          = step.value["type"]
    }
  }

  dynamic "variable" {
    for_each = var.variable
    content {
      example = variable.value["example"]
      id      = variable.value["id"]
      name    = variable.value["name"]
      pattern = variable.value["pattern"]
      type    = variable.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = datadog_synthetics_test.this.id
}

output "monitor_id" {
  description = "returns a number"
  value       = datadog_synthetics_test.this.monitor_id
}

output "this" {
  value = datadog_synthetics_test.this
}
```

[top](#index)