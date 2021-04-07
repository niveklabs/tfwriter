# cloudflare_rate_limit

[back](../cloudflare.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    cloudflare = ">= 2.19.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_rate_limit" {
  source = "./modules/cloudflare/r/cloudflare_rate_limit"

  # bypass_url_patterns - (optional) is a type of set of string
  bypass_url_patterns = []
  # description - (optional) is a type of string
  description = null
  # disabled - (optional) is a type of bool
  disabled = null
  # period - (required) is a type of number
  period = null
  # threshold - (required) is a type of number
  threshold = null
  # zone_id - (required) is a type of string
  zone_id = null

  action = [{
    mode = null
    response = [{
      body         = null
      content_type = null
    }]
    timeout = null
  }]

  correlate = [{
    by = null
  }]

  match = [{
    request = [{
      methods     = []
      schemes     = []
      url_pattern = null
    }]
    response = [{
      headers        = [{}]
      origin_traffic = null
      statuses       = []
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bypass_url_patterns" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "period" {
  description = "(required)"
  type        = number
}

variable "threshold" {
  description = "(required)"
  type        = number
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "action" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      mode = string
      response = list(object(
        {
          body         = string
          content_type = string
        }
      ))
      timeout = number
    }
  ))
}

variable "correlate" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      by = string
    }
  ))
  default = []
}

variable "match" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      request = list(object(
        {
          methods     = set(string)
          schemes     = set(string)
          url_pattern = string
        }
      ))
      response = list(object(
        {
          headers        = list(map(string))
          origin_traffic = bool
          statuses       = set(number)
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_rate_limit" "this" {
  # bypass_url_patterns - (optional) is a type of set of string
  bypass_url_patterns = var.bypass_url_patterns
  # description - (optional) is a type of string
  description = var.description
  # disabled - (optional) is a type of bool
  disabled = var.disabled
  # period - (required) is a type of number
  period = var.period
  # threshold - (required) is a type of number
  threshold = var.threshold
  # zone_id - (required) is a type of string
  zone_id = var.zone_id

  dynamic "action" {
    for_each = var.action
    content {
      # mode - (required) is a type of string
      mode = action.value["mode"]
      # timeout - (optional) is a type of number
      timeout = action.value["timeout"]

      dynamic "response" {
        for_each = action.value.response
        content {
          # body - (required) is a type of string
          body = response.value["body"]
          # content_type - (required) is a type of string
          content_type = response.value["content_type"]
        }
      }

    }
  }

  dynamic "correlate" {
    for_each = var.correlate
    content {
      # by - (optional) is a type of string
      by = correlate.value["by"]
    }
  }

  dynamic "match" {
    for_each = var.match
    content {

      dynamic "request" {
        for_each = match.value.request
        content {
          # methods - (optional) is a type of set of string
          methods = request.value["methods"]
          # schemes - (optional) is a type of set of string
          schemes = request.value["schemes"]
          # url_pattern - (optional) is a type of string
          url_pattern = request.value["url_pattern"]
        }
      }

      dynamic "response" {
        for_each = match.value.response
        content {
          # headers - (optional) is a type of list of map of string
          headers = response.value["headers"]
          # origin_traffic - (optional) is a type of bool
          origin_traffic = response.value["origin_traffic"]
          # statuses - (optional) is a type of set of number
          statuses = response.value["statuses"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_rate_limit.this.id
}

output "this" {
  value = cloudflare_rate_limit.this
}
```

[top](#index)