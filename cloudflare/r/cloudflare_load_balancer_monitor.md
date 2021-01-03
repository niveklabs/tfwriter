# cloudflare_load_balancer_monitor

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
    cloudflare = ">= 2.15.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "cloudflare_load_balancer_monitor" {
  source = "./modules/cloudflare/r/cloudflare_load_balancer_monitor"

  # allow_insecure - (optional) is a type of bool
  allow_insecure = null
  # description - (optional) is a type of string
  description = null
  # expected_body - (optional) is a type of string
  expected_body = null
  # expected_codes - (optional) is a type of string
  expected_codes = null
  # follow_redirects - (optional) is a type of bool
  follow_redirects = null
  # interval - (optional) is a type of number
  interval = null
  # method - (optional) is a type of string
  method = null
  # path - (optional) is a type of string
  path = null
  # port - (optional) is a type of number
  port = null
  # retries - (optional) is a type of number
  retries = null
  # timeout - (optional) is a type of number
  timeout = null
  # type - (optional) is a type of string
  type = null

  header = [{
    header = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allow_insecure" {
  description = "(optional)"
  type        = bool
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
  type        = string
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

variable "timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
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
```

[top](#index)

### Resource

```terraform
resource "cloudflare_load_balancer_monitor" "this" {
  allow_insecure   = var.allow_insecure
  description      = var.description
  expected_body    = var.expected_body
  expected_codes   = var.expected_codes
  follow_redirects = var.follow_redirects
  interval         = var.interval
  method           = var.method
  path             = var.path
  port             = var.port
  retries          = var.retries
  timeout          = var.timeout
  type             = var.type

  dynamic "header" {
    for_each = var.header
    content {
      header = header.value["header"]
      values = header.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_on" {
  description = "returns a string"
  value       = cloudflare_load_balancer_monitor.this.created_on
}

output "id" {
  description = "returns a string"
  value       = cloudflare_load_balancer_monitor.this.id
}

output "method" {
  description = "returns a string"
  value       = cloudflare_load_balancer_monitor.this.method
}

output "modified_on" {
  description = "returns a string"
  value       = cloudflare_load_balancer_monitor.this.modified_on
}

output "path" {
  description = "returns a string"
  value       = cloudflare_load_balancer_monitor.this.path
}

output "this" {
  value = cloudflare_load_balancer_monitor.this
}
```

[top](#index)