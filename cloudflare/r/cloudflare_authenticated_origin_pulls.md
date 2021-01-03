# cloudflare_authenticated_origin_pulls

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
module "cloudflare_authenticated_origin_pulls" {
  source = "./modules/cloudflare/r/cloudflare_authenticated_origin_pulls"

  # authenticated_origin_pulls_certificate - (optional) is a type of string
  authenticated_origin_pulls_certificate = null
  # enabled - (required) is a type of bool
  enabled = null
  # hostname - (optional) is a type of string
  hostname = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "authenticated_origin_pulls_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "hostname" {
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
resource "cloudflare_authenticated_origin_pulls" "this" {
  authenticated_origin_pulls_certificate = var.authenticated_origin_pulls_certificate
  enabled                                = var.enabled
  hostname                               = var.hostname
  zone_id                                = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_authenticated_origin_pulls.this.id
}

output "this" {
  value = cloudflare_authenticated_origin_pulls.this
}
```

[top](#index)