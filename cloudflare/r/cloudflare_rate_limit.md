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
  bypass_url_patterns = var.bypass_url_patterns
  description         = var.description
  disabled            = var.disabled
  period              = var.period
  threshold           = var.threshold
  zone_id             = var.zone_id

  dynamic "action" {
    for_each = var.action
    content {
      mode    = action.value["mode"]
      timeout = action.value["timeout"]

      dynamic "response" {
        for_each = action.value.response
        content {
          body         = response.value["body"]
          content_type = response.value["content_type"]
        }
      }

    }
  }

  dynamic "correlate" {
    for_each = var.correlate
    content {
      by = correlate.value["by"]
    }
  }

  dynamic "match" {
    for_each = var.match
    content {

      dynamic "request" {
        for_each = match.value.request
        content {
          methods     = request.value["methods"]
          schemes     = request.value["schemes"]
          url_pattern = request.value["url_pattern"]
        }
      }

      dynamic "response" {
        for_each = match.value.response
        content {
          headers        = response.value["headers"]
          origin_traffic = response.value["origin_traffic"]
          statuses       = response.value["statuses"]
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