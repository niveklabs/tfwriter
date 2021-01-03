# cloudflare_logpull_retention

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
module "cloudflare_logpull_retention" {
  source = "./modules/cloudflare/r/cloudflare_logpull_retention"

  # enabled - (required) is a type of bool
  enabled = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "enabled" {
  description = "(required)"
  type        = bool
}

variable "zone_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_logpull_retention" "this" {
  enabled = var.enabled
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_logpull_retention.this.id
}

output "this" {
  value = cloudflare_logpull_retention.this
}
```

[top](#index)