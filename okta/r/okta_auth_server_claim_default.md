# okta_auth_server_claim_default

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_auth_server_claim_default" {
  source = "./modules/okta/r/okta_auth_server_claim_default"

  # auth_server_id - (required) is a type of string
  auth_server_id = null
  # name - (required) is a type of string
  name = null
  # value - (optional) is a type of string
  value = null
}
```

[top](#index)

### Variables

```terraform
variable "auth_server_id" {
  description = "(required) - Auth server ID"
  type        = string
}

variable "name" {
  description = "(required) - Default auth server claim name"
  type        = string
}

variable "value" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_auth_server_claim_default" "this" {
  auth_server_id = var.auth_server_id
  name           = var.name
  value          = var.value
}
```

[top](#index)

### Outputs

```terraform
output "always_include_in_token" {
  description = "returns a bool"
  value       = okta_auth_server_claim_default.this.always_include_in_token
}

output "claim_type" {
  description = "returns a string"
  value       = okta_auth_server_claim_default.this.claim_type
}

output "id" {
  description = "returns a string"
  value       = okta_auth_server_claim_default.this.id
}

output "scopes" {
  description = "returns a set of string"
  value       = okta_auth_server_claim_default.this.scopes
}

output "status" {
  description = "returns a string"
  value       = okta_auth_server_claim_default.this.status
}

output "value_type" {
  description = "returns a string"
  value       = okta_auth_server_claim_default.this.value_type
}

output "this" {
  value = okta_auth_server_claim_default.this
}
```

[top](#index)