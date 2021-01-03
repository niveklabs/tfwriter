# cloudflare_filter

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
module "cloudflare_filter" {
  source = "./modules/cloudflare/r/cloudflare_filter"

  # description - (optional) is a type of string
  description = null
  # expression - (required) is a type of string
  expression = null
  # paused - (optional) is a type of bool
  paused = null
  # ref - (optional) is a type of string
  ref = null
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

variable "expression" {
  description = "(required)"
  type        = string
}

variable "paused" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ref" {
  description = "(optional)"
  type        = string
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
resource "cloudflare_filter" "this" {
  description = var.description
  expression  = var.expression
  paused      = var.paused
  ref         = var.ref
  zone_id     = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_filter.this.id
}

output "this" {
  value = cloudflare_filter.this
}
```

[top](#index)