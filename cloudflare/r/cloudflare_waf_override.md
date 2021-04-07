# cloudflare_waf_override

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
module "cloudflare_waf_override" {
  source = "./modules/cloudflare/r/cloudflare_waf_override"

  # description - (optional) is a type of string
  description = null
  # groups - (optional) is a type of map of string
  groups = {}
  # paused - (optional) is a type of bool
  paused = null
  # priority - (optional) is a type of number
  priority = null
  # rewrite_action - (optional) is a type of map of string
  rewrite_action = {}
  # rules - (required) is a type of map of string
  rules = {}
  # urls - (required) is a type of list of string
  urls = []
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "groups" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "paused" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "priority" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "rewrite_action" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "rules" {
  description = "(required)"
  type        = map(string)
}

variable "urls" {
  description = "(required)"
  type        = list(string)
}

variable "zone_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_waf_override" "this" {
  # description - (optional) is a type of string
  description = var.description
  # groups - (optional) is a type of map of string
  groups = var.groups
  # paused - (optional) is a type of bool
  paused = var.paused
  # priority - (optional) is a type of number
  priority = var.priority
  # rewrite_action - (optional) is a type of map of string
  rewrite_action = var.rewrite_action
  # rules - (required) is a type of map of string
  rules = var.rules
  # urls - (required) is a type of list of string
  urls = var.urls
  # zone_id - (required) is a type of string
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_waf_override.this.id
}

output "override_id" {
  description = "returns a string"
  value       = cloudflare_waf_override.this.override_id
}

output "this" {
  value = cloudflare_waf_override.this
}
```

[top](#index)