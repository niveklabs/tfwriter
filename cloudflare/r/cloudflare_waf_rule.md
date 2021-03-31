# cloudflare_waf_rule

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
module "cloudflare_waf_rule" {
  source = "./modules/cloudflare/r/cloudflare_waf_rule"

  # mode - (required) is a type of string
  mode = null
  # package_id - (optional) is a type of string
  package_id = null
  # rule_id - (required) is a type of string
  rule_id = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "mode" {
  description = "(required)"
  type        = string
}

variable "package_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule_id" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_waf_rule" "this" {
  mode       = var.mode
  package_id = var.package_id
  rule_id    = var.rule_id
  zone_id    = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "group_id" {
  description = "returns a string"
  value       = cloudflare_waf_rule.this.group_id
}

output "id" {
  description = "returns a string"
  value       = cloudflare_waf_rule.this.id
}

output "package_id" {
  description = "returns a string"
  value       = cloudflare_waf_rule.this.package_id
}

output "this" {
  value = cloudflare_waf_rule.this
}
```

[top](#index)