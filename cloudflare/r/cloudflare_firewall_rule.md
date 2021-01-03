# cloudflare_firewall_rule

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
module "cloudflare_firewall_rule" {
  source = "./modules/cloudflare/r/cloudflare_firewall_rule"

  # action - (required) is a type of string
  action = null
  # description - (optional) is a type of string
  description = null
  # filter_id - (required) is a type of string
  filter_id = null
  # paused - (optional) is a type of bool
  paused = null
  # priority - (optional) is a type of number
  priority = null
  # products - (optional) is a type of set of string
  products = []
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "action" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_id" {
  description = "(required)"
  type        = string
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

variable "products" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "zone_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_firewall_rule" "this" {
  action      = var.action
  description = var.description
  filter_id   = var.filter_id
  paused      = var.paused
  priority    = var.priority
  products    = var.products
  zone_id     = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_firewall_rule.this.id
}

output "this" {
  value = cloudflare_firewall_rule.this
}
```

[top](#index)