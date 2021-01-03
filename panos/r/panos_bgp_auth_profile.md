# panos_bgp_auth_profile

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_bgp_auth_profile" {
  source = "./modules/panos/r/panos_bgp_auth_profile"

  # name - (required) is a type of string
  name = null
  # secret - (optional) is a type of string
  secret = null
  # virtual_router - (required) is a type of string
  virtual_router = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "virtual_router" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "panos_bgp_auth_profile" "this" {
  name           = var.name
  secret         = var.secret
  virtual_router = var.virtual_router
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_bgp_auth_profile.this.id
}

output "secret_enc" {
  description = "returns a string"
  value       = panos_bgp_auth_profile.this.secret_enc
  sensitive   = true
}

output "this" {
  value = panos_bgp_auth_profile.this
}
```

[top](#index)