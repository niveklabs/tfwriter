# cloudflare_custom_hostname_fallback_origin

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
module "cloudflare_custom_hostname_fallback_origin" {
  source = "./modules/cloudflare/r/cloudflare_custom_hostname_fallback_origin"

  # origin - (required) is a type of string
  origin = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "origin" {
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
resource "cloudflare_custom_hostname_fallback_origin" "this" {
  # origin - (required) is a type of string
  origin = var.origin
  # zone_id - (required) is a type of string
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_custom_hostname_fallback_origin.this.id
}

output "status" {
  description = "returns a string"
  value       = cloudflare_custom_hostname_fallback_origin.this.status
}

output "this" {
  value = cloudflare_custom_hostname_fallback_origin.this
}
```

[top](#index)