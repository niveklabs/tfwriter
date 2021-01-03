# cloudflare_waf_group

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
module "cloudflare_waf_group" {
  source = "./modules/cloudflare/r/cloudflare_waf_group"

  # group_id - (required) is a type of string
  group_id = null
  # mode - (optional) is a type of string
  mode = null
  # package_id - (optional) is a type of string
  package_id = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(required)"
  type        = string
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "package_id" {
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
resource "cloudflare_waf_group" "this" {
  group_id   = var.group_id
  mode       = var.mode
  package_id = var.package_id
  zone_id    = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_waf_group.this.id
}

output "package_id" {
  description = "returns a string"
  value       = cloudflare_waf_group.this.package_id
}

output "this" {
  value = cloudflare_waf_group.this
}
```

[top](#index)