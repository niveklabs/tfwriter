# cloudflare_logpush_ownership_challenge

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
module "cloudflare_logpush_ownership_challenge" {
  source = "./modules/cloudflare/r/cloudflare_logpush_ownership_challenge"

  # destination_conf - (required) is a type of string
  destination_conf = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "destination_conf" {
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
resource "cloudflare_logpush_ownership_challenge" "this" {
  # destination_conf - (required) is a type of string
  destination_conf = var.destination_conf
  # zone_id - (required) is a type of string
  zone_id = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_logpush_ownership_challenge.this.id
}

output "ownership_challenge_filename" {
  description = "returns a string"
  value       = cloudflare_logpush_ownership_challenge.this.ownership_challenge_filename
}

output "this" {
  value = cloudflare_logpush_ownership_challenge.this
}
```

[top](#index)