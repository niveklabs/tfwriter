# cloudflare_zone

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
module "cloudflare_zone" {
  source = "./modules/cloudflare/r/cloudflare_zone"

  # jump_start - (optional) is a type of bool
  jump_start = null
  # paused - (optional) is a type of bool
  paused = null
  # plan - (optional) is a type of string
  plan = null
  # type - (optional) is a type of string
  type = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "jump_start" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "paused" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "plan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "cloudflare_zone" "this" {
  jump_start = var.jump_start
  paused     = var.paused
  plan       = var.plan
  type       = var.type
  zone       = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = cloudflare_zone.this.id
}

output "meta" {
  description = "returns a map of string"
  value       = cloudflare_zone.this.meta
}

output "name_servers" {
  description = "returns a list of string"
  value       = cloudflare_zone.this.name_servers
}

output "plan" {
  description = "returns a string"
  value       = cloudflare_zone.this.plan
}

output "status" {
  description = "returns a string"
  value       = cloudflare_zone.this.status
}

output "vanity_name_servers" {
  description = "returns a list of string"
  value       = cloudflare_zone.this.vanity_name_servers
}

output "verification_key" {
  description = "returns a string"
  value       = cloudflare_zone.this.verification_key
}

output "this" {
  value = cloudflare_zone.this
}
```

[top](#index)