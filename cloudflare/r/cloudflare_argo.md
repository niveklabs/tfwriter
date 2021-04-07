# cloudflare_argo

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
module "cloudflare_argo" {
  source = "./modules/cloudflare/r/cloudflare_argo"

  # smart_routing - (optional) is a type of string
  smart_routing = null
  # tiered_caching - (optional) is a type of string
  tiered_caching = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "smart_routing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tiered_caching" {
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
resource "cloudflare_argo" "this" {
  # smart_routing - (optional) is a type of string
  smart_routing = var.smart_routing
  # tiered_caching - (optional) is a type of string
  tiered_caching = var.tiered_caching
  # zone_id - (required) is a type of string
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_argo.this.id
}

output "this" {
  value = cloudflare_argo.this
}
```

[top](#index)