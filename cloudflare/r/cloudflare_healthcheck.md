# cloudflare_healthcheck

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
module "cloudflare_healthcheck" {
  source = "./modules/cloudflare/r/cloudflare_healthcheck"

  # address - (required) is a type of string
  address = null
  # allow_insecure - (optional) is a type of bool
  allow_insecure = null
  # check_regions - (optional) is a type of list of string
  check_regions = []
  # consecutive_fails - (optional) is a type of number
  consecutive_fails = null
  # consecutive_successes - (optional) is a type of number
  consecutive_successes = null
  # description - (optional) is a type of string
  description = null
  # expected_body - (optional) is a type of string
  expected_body = null
  # expected_codes - (optional) is a type of list of string
  expected_codes = []
  # follow_redirects - (optional) is a type of bool
  follow_redirects = null
  # interval - (optional) is a type of number
  interval = null
  # method - (optional) is a type of string
  method = null
  # name - (required) is a type of string
  name = null
  # notification_email_addresses - (optional) is a type of list of string
  notification_email_addresses = []
  # notification_suspended - (optional) is a type of bool
  notification_suspended = null
  # path - (optional) is a type of string
  path = null
  # port - (optional) is a type of number
  port = null
  # retries - (optional) is a type of number
  retries = null
  # suspended - (optional) is a type of bool
  suspended = null
  # timeout - (optional) is a type of number
  timeout = null
  # type - (required) is a type of string
  type = null
  # zone_id - (required) is a type of string
  zone_id = null

  header = [{
    header = null
    values = []
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required)"
  type        = string
}

variable "allow_insecure" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "check_regions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "consecutive_fails" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "consecutive_successes" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expected_body" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "expected_codes" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "follow_redirects" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "notification_email_addresses" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "notification_suspended" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "retries" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "suspended" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(required)"
  type        = string
}

variable "header" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      header = string
      values = set(string)
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_healthcheck" "this" {
  # address - (required) is a type of string
  address = var.address
  # allow_insecure - (optional) is a type of bool
  allow_insecure = var.allow_insecure
  # check_regions - (optional) is a type of list of string
  check_regions = var.check_regions
  # consecutive_fails - (optional) is a type of number
  consecutive_fails = var.consecutive_fails
  # consecutive_successes - (optional) is a type of number
  consecutive_successes = var.consecutive_successes
  # description - (optional) is a type of string
  description = var.description
  # expected_body - (optional) is a type of string
  expected_body = var.expected_body
  # expected_codes - (optional) is a type of list of string
  expected_codes = var.expected_codes
  # follow_redirects - (optional) is a type of bool
  follow_redirects = var.follow_redirects
  # interval - (optional) is a type of number
  interval = var.interval
  # method - (optional) is a type of string
  method = var.method
  # name - (required) is a type of string
  name = var.name
  # notification_email_addresses - (optional) is a type of list of string
  notification_email_addresses = var.notification_email_addresses
  # notification_suspended - (optional) is a type of bool
  notification_suspended = var.notification_suspended
  # path - (optional) is a type of string
  path = var.path
  # port - (optional) is a type of number
  port = var.port
  # retries - (optional) is a type of number
  retries = var.retries
  # suspended - (optional) is a type of bool
  suspended = var.suspended
  # timeout - (optional) is a type of number
  timeout = var.timeout
  # type - (required) is a type of string
  type = var.type
  # zone_id - (required) is a type of string
  zone_id = var.zone_id

  dynamic "header" {
    for_each = var.header
    content {
      # header - (required) is a type of string
      header = header.value["header"]
      # values - (required) is a type of set of string
      values = header.value["values"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "check_regions" {
  description = "returns a list of string"
  value       = cloudflare_healthcheck.this.check_regions
}

output "created_on" {
  description = "returns a string"
  value       = cloudflare_healthcheck.this.created_on
}

output "id" {
  description = "returns a string"
  value       = cloudflare_healthcheck.this.id
}

output "method" {
  description = "returns a string"
  value       = cloudflare_healthcheck.this.method
}

output "modified_on" {
  description = "returns a string"
  value       = cloudflare_healthcheck.this.modified_on
}

output "this" {
  value = cloudflare_healthcheck.this
}
```

[top](#index)