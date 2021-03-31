# cloudflare_access_service_token

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
module "cloudflare_access_service_token" {
  source = "./modules/cloudflare/r/cloudflare_access_service_token"

  # account_id - (optional) is a type of string
  account_id = null
  # name - (required) is a type of string
  name = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```terraform
variable "account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
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
resource "cloudflare_access_service_token" "this" {
  account_id = var.account_id
  name       = var.name
  zone_id    = var.zone_id
}
```

[top](#index)

### Outputs

```terraform
output "client_id" {
  description = "returns a string"
  value       = cloudflare_access_service_token.this.client_id
}

output "client_secret" {
  description = "returns a string"
  value       = cloudflare_access_service_token.this.client_secret
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = cloudflare_access_service_token.this.id
}

output "this" {
  value = cloudflare_access_service_token.this
}
```

[top](#index)