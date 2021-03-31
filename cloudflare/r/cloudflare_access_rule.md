# cloudflare_access_rule

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
module "cloudflare_access_rule" {
  source = "./modules/cloudflare/r/cloudflare_access_rule"

  # configuration - (required) is a type of map of string
  configuration = {}
  # mode - (required) is a type of string
  mode = null
  # notes - (optional) is a type of string
  notes = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "configuration" {
  description = "(required)"
  type        = map(string)
}

variable "mode" {
  description = "(required)"
  type        = string
}

variable "notes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_access_rule" "this" {
  configuration = var.configuration
  mode          = var.mode
  notes         = var.notes
  zone_id       = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_access_rule.this.id
}

output "zone_id" {
  description = "returns a string"
  value       = cloudflare_access_rule.this.zone_id
}

output "this" {
  value = cloudflare_access_rule.this
}
```

[top](#index)