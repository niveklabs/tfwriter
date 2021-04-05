# okta_auth_server

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "okta_auth_server" {
  source = "./modules/okta/d/okta_auth_server"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "okta_auth_server" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "audiences" {
  description = "returns a set of string"
  value       = data.okta_auth_server.this.audiences
}

output "credentials_last_rotated" {
  description = "returns a string"
  value       = data.okta_auth_server.this.credentials_last_rotated
}

output "credentials_next_rotation" {
  description = "returns a string"
  value       = data.okta_auth_server.this.credentials_next_rotation
}

output "credentials_rotation_mode" {
  description = "returns a string"
  value       = data.okta_auth_server.this.credentials_rotation_mode
}

output "description" {
  description = "returns a string"
  value       = data.okta_auth_server.this.description
}

output "id" {
  description = "returns a string"
  value       = data.okta_auth_server.this.id
}

output "issuer" {
  description = "returns a string"
  value       = data.okta_auth_server.this.issuer
}

output "issuer_mode" {
  description = "returns a string"
  value       = data.okta_auth_server.this.issuer_mode
}

output "kid" {
  description = "returns a string"
  value       = data.okta_auth_server.this.kid
}

output "status" {
  description = "returns a string"
  value       = data.okta_auth_server.this.status
}

output "this" {
  value = okta_auth_server.this
}
```

[top](#index)