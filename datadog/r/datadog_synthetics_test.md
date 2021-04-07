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
    datadog = ">= 2.24.0"
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
  # locations - (required) is a type of set of string
  locations = []
  # message - (optional) is a type of string
  message = null
  # name - (required) is a type of string
  name = null
  # options - (optional) is a type of map of string
  options = {}
  # request - (optional) is a type of map of string
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

  browser_step = [{
    allow_failure        = null
    force_element_update = null
    name                 = null
    params = [{
      attribute         = null
      check             = null
      click_type        = null
      code              = null
      delay             = null
      element           = null
      email             = null
      file              = null
      files             = null
      modifiers         = []
      playing_tab_id    = null
      request           = null
      subtest_public_id = null
      value             = null
      variable = [{
        example = null
        name    = null
      }]
      with_click = null
      x          = null
      y          = null
    }]
    timeout = null
    type    = null
  }]

  browser_variable = [{
    example = null
    id      = null
    name    = null
    pattern = null
    type    = null
  }]

  config_variable = [{
    example = null
    name    = null
    pattern = null
    type    = null
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

  request_definition = [{
    body       = null
    dns_server = null
    host       = null
    method     = null
    port       = null
    timeout    = null
    url        = null
  }]

  step = [{
    allow_failure        = null
    force_element_update = null
    name                 = null
    params               = null
    timeout              = null
    type                 = null
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
  description = "(optional) - List of assertions. **Deprecated.** Define `assertion` blocks instead."
  type        = list(map(string))
  default     = null
}

variable "device_ids" {
  description = "(optional) - Array with the different device IDs used to run the test. Allowed enum values: `laptop_large`, `tablet`, `mobile_small` (only available for `browser` tests)."
  type        = list(string)
  default     = null
}

variable "locations" {
  description = "(required) - Array of locations used to run the test. Refer to [Datadog documentation](https://docs.datadoghq.com/synthetics/api_test/#request) for available locations (e.g. `aws:eu-central-1`)."
  type        = set(string)
}

variable "message" {
  description = "(optional) - A message to include with notifications for this synthetics test. Email notifications can be sent to specific users by using the same `@username` notation as events."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of Datadog synthetics test."
  type        = string
}

variable "options" {
  description = "(optional) - **Deprecated.** Define `options_list` blocks instead."
  type        = map(string)
  default     = null
}

variable "request" {
  description = "(optional) - The synthetics test request. Required if `type = \"api\"`. **Deprecated.** Define `request_definition` list with one element instead."
  type        = map(string)
  default     = null
}

variable "request_headers" {
  description = "(optional) - Header name and value map."
  type        = map(string)
  default     = null
}

variable "request_query" {
  description = "(optional) - Query arguments name and value map."
  type        = map(string)
  default     = null
}

variable "status" {
  description = "(required) - Define whether you want to start (`live`) or pause (`paused`) a Synthetic test. Allowed enum values: `live`, `paused`"
  type        = string
}

variable "subtype" {
  description = "(optional) - When `type` is `api`, choose from `http`, `ssl`, `tcp` or `dns`. Defaults to `http`."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - A list of tags to associate with your synthetics test. This can help you categorize and filter tests in the manage synthetics page of the UI. Default is an empty list (`[]`)."
  type        = list(string)
  default     = null
}

variable "type" {
  description = "(required) - Synthetics test type (`api` or `browser`)."
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

variable "browser_step" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allow_failure        = bool
      force_element_update = bool
      name                 = string
      params = list(object(
        {
          attribute         = string
          check             = string
          click_type        = string
          code              = string
          delay             = number
          element           = string
          email             = string
          file              = string
          files             = string
          modifiers         = list(string)
          playing_tab_id    = string
          request           = string
          subtest_public_id = string
          value             = string
          variable = list(object(
            {
              example = string
              name    = string
            }
          ))
          with_click = bool
          x          = number
          y          = number
        }
      ))
      timeout = number
      type    = string
    }
  ))
  default = []
}

variable "browser_variable" {
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

variable "config_variable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      example = string
      name    = string
      pattern = string
      type    = string
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

variable "request_definition" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      body       = string
      dns_server = string
      host       = string
      method     = string
      port       = number
      timeout    = number
      url        = string
    }
  ))
  default = []
}

variable "step" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allow_failure        = bool
      force_element_update = bool
      name                 = string
      params               = string
      timeout              = number
      type                 = string
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
  # assertions - (optional) is a type of list of map of string
  assertions = var.assertions
  # device_ids - (optional) is a type of list of string
  device_ids = var.device_ids
  # locations - (required) is a type of set of string
  locations = var.locations
  # message - (optional) is a type of string
  message = var.message
  # name - (required) is a type of string
  name = var.name
  # options - (optional) is a type of map of string
  options = var.options
  # request - (optional) is a type of map of string
  request = var.request
  # request_headers - (optional) is a type of map of string
  request_headers = var.request_headers
  # request_query - (optional) is a type of map of string
  request_query = var.request_query
  # status - (required) is a type of string
  status = var.status
  # subtype - (optional) is a type of string
  subtype = var.subtype
  # tags - (optional) is a type of list of string
  tags = var.tags
  # type - (required) is a type of string
  type = var.type

  dynamic "assertion" {
    for_each = var.assertion
    content {
      # operator - (required) is a type of string
      operator = assertion.value["operator"]
      # property - (optional) is a type of string
      property = assertion.value["property"]
      # target - (optional) is a type of string
      target = assertion.value["target"]
      # type - (required) is a type of string
      type = assertion.value["type"]

      dynamic "targetjsonpath" {
        for_each = assertion.value.targetjsonpath
        content {
          # jsonpath - (required) is a type of string
          jsonpath = targetjsonpath.value["jsonpath"]
          # operator - (required) is a type of string
          operator = targetjsonpath.value["operator"]
          # targetvalue - (required) is a type of string
          targetvalue = targetjsonpath.value["targetvalue"]
        }
      }

    }
  }

  dynamic "browser_step" {
    for_each = var.browser_step
    content {
      # allow_failure - (optional) is a type of bool
      allow_failure = browser_step.value["allow_failure"]
      # force_element_update - (optional) is a type of bool
      force_element_update = browser_step.value["force_element_update"]
      # name - (required) is a type of string
      name = browser_step.value["name"]
      # timeout - (optional) is a type of number
      timeout = browser_step.value["timeout"]
      # type - (required) is a type of string
      type = browser_step.value["type"]

      dynamic "params" {
        for_each = browser_step.value.params
        content {
          # attribute - (optional) is a type of string
          attribute = params.value["attribute"]
          # check - (optional) is a type of string
          check = params.value["check"]
          # click_type - (optional) is a type of string
          click_type = params.value["click_type"]
          # code - (optional) is a type of string
          code = params.value["code"]
          # delay - (optional) is a type of number
          delay = params.value["delay"]
          # element - (optional) is a type of string
          element = params.value["element"]
          # email - (optional) is a type of string
          email = params.value["email"]
          # file - (optional) is a type of string
          file = params.value["file"]
          # files - (optional) is a type of string
          files = params.value["files"]
          # modifiers - (optional) is a type of list of string
          modifiers = params.value["modifiers"]
          # playing_tab_id - (optional) is a type of string
          playing_tab_id = params.value["playing_tab_id"]
          # request - (optional) is a type of string
          request = params.value["request"]
          # subtest_public_id - (optional) is a type of string
          subtest_public_id = params.value["subtest_public_id"]
          # value - (optional) is a type of string
          value = params.value["value"]
          # with_click - (optional) is a type of bool
          with_click = params.value["with_click"]
          # x - (optional) is a type of number
          x = params.value["x"]
          # y - (optional) is a type of number
          y = params.value["y"]

          dynamic "variable" {
            for_each = params.value.variable
            content {
              # example - (optional) is a type of string
              example = variable.value["example"]
              # name - (optional) is a type of string
              name = variable.value["name"]
            }
          }

        }
      }

    }
  }

  dynamic "browser_variable" {
    for_each = var.browser_variable
    content {
      # example - (optional) is a type of string
      example = browser_variable.value["example"]
      # id - (optional) is a type of string
      id = browser_variable.value["id"]
      # name - (required) is a type of string
      name = browser_variable.value["name"]
      # pattern - (optional) is a type of string
      pattern = browser_variable.value["pattern"]
      # type - (required) is a type of string
      type = browser_variable.value["type"]
    }
  }

  dynamic "config_variable" {
    for_each = var.config_variable
    content {
      # example - (optional) is a type of string
      example = config_variable.value["example"]
      # name - (required) is a type of string
      name = config_variable.value["name"]
      # pattern - (optional) is a type of string
      pattern = config_variable.value["pattern"]
      # type - (required) is a type of string
      type = config_variable.value["type"]
    }
  }

  dynamic "options_list" {
    for_each = var.options_list
    content {
      # accept_self_signed - (optional) is a type of bool
      accept_self_signed = options_list.value["accept_self_signed"]
      # allow_insecure - (optional) is a type of bool
      allow_insecure = options_list.value["allow_insecure"]
      # follow_redirects - (optional) is a type of bool
      follow_redirects = options_list.value["follow_redirects"]
      # min_failure_duration - (optional) is a type of number
      min_failure_duration = options_list.value["min_failure_duration"]
      # min_location_failed - (optional) is a type of number
      min_location_failed = options_list.value["min_location_failed"]
      # tick_every - (optional) is a type of number
      tick_every = options_list.value["tick_every"]

      dynamic "monitor_options" {
        for_each = options_list.value.monitor_options
        content {
          # renotify_interval - (optional) is a type of number
          renotify_interval = monitor_options.value["renotify_interval"]
        }
      }

      dynamic "retry" {
        for_each = options_list.value.retry
        content {
          # count - (optional) is a type of number
          count = retry.value["count"]
          # interval - (optional) is a type of number
          interval = retry.value["interval"]
        }
      }

    }
  }

  dynamic "request_basicauth" {
    for_each = var.request_basicauth
    content {
      # password - (required) is a type of string
      password = request_basicauth.value["password"]
      # username - (required) is a type of string
      username = request_basicauth.value["username"]
    }
  }

  dynamic "request_client_certificate" {
    for_each = var.request_client_certificate
    content {

      dynamic "cert" {
        for_each = request_client_certificate.value.cert
        content {
          # content - (required) is a type of string
          content = cert.value["content"]
          # filename - (optional) is a type of string
          filename = cert.value["filename"]
        }
      }

      dynamic "key" {
        for_each = request_client_certificate.value.key
        content {
          # content - (required) is a type of string
          content = key.value["content"]
          # filename - (optional) is a type of string
          filename = key.value["filename"]
        }
      }

    }
  }

  dynamic "request_definition" {
    for_each = var.request_definition
    content {
      # body - (optional) is a type of string
      body = request_definition.value["body"]
      # dns_server - (optional) is a type of string
      dns_server = request_definition.value["dns_server"]
      # host - (optional) is a type of string
      host = request_definition.value["host"]
      # method - (optional) is a type of string
      method = request_definition.value["method"]
      # port - (optional) is a type of number
      port = request_definition.value["port"]
      # timeout - (optional) is a type of number
      timeout = request_definition.value["timeout"]
      # url - (optional) is a type of string
      url = request_definition.value["url"]
    }
  }

  dynamic "step" {
    for_each = var.step
    content {
      # allow_failure - (optional) is a type of bool
      allow_failure = step.value["allow_failure"]
      # force_element_update - (optional) is a type of bool
      force_element_update = step.value["force_element_update"]
      # name - (required) is a type of string
      name = step.value["name"]
      # params - (required) is a type of string
      params = step.value["params"]
      # timeout - (optional) is a type of number
      timeout = step.value["timeout"]
      # type - (required) is a type of string
      type = step.value["type"]
    }
  }

  dynamic "variable" {
    for_each = var.variable
    content {
      # example - (optional) is a type of string
      example = variable.value["example"]
      # id - (optional) is a type of string
      id = variable.value["id"]
      # name - (required) is a type of string
      name = variable.value["name"]
      # pattern - (optional) is a type of string
      pattern = variable.value["pattern"]
      # type - (required) is a type of string
      type = variable.value["type"]
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