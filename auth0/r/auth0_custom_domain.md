# auth0_custom_domain

[back](../auth0.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    auth0 = ">= 0.14.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "auth0_custom_domain" {
  source = "./modules/auth0/r/auth0_custom_domain"

  # domain - (required) is a type of string
  domain = null
  # type - (required) is a type of string
  type = null
  # verification_method - (required) is a type of string
  verification_method = null
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}

variable "verification_method" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "auth0_custom_domain" "this" {
  # domain - (required) is a type of string
  domain = var.domain
  # type - (required) is a type of string
  type = var.type
  # verification_method - (required) is a type of string
  verification_method = var.verification_method
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = auth0_custom_domain.this.id
}

output "primary" {
  description = "returns a bool"
  value       = auth0_custom_domain.this.primary
}

output "status" {
  description = "returns a string"
  value       = auth0_custom_domain.this.status
}

output "verification" {
  description = "returns a list of object"
  value       = auth0_custom_domain.this.verification
}

output "this" {
  value = auth0_custom_domain.this
}
```

[top](#index)