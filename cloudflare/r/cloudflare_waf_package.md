# cloudflare_waf_package

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
module "cloudflare_waf_package" {
  source = "./modules/cloudflare/r/cloudflare_waf_package"

  # action_mode - (optional) is a type of string
  action_mode = null
  # package_id - (required) is a type of string
  package_id = null
  # sensitivity - (optional) is a type of string
  sensitivity = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "action_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "package_id" {
  description = "(required)"
  type        = string
}

variable "sensitivity" {
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
resource "cloudflare_waf_package" "this" {
  action_mode = var.action_mode
  package_id  = var.package_id
  sensitivity = var.sensitivity
  zone_id     = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_waf_package.this.id
}

output "this" {
  value = cloudflare_waf_package.this
}
```

[top](#index)