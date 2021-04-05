# okta_idp_oidc

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
module "okta_idp_oidc" {
  source = "./modules/okta/d/okta_idp_oidc"

  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "okta_idp_oidc" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "authorization_binding" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.authorization_binding
}

output "authorization_url" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.authorization_url
}

output "client_id" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.client_id
}

output "client_secret" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.client_secret
  sensitive   = true
}

output "id" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.id
}

output "issuer_mode" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.issuer_mode
}

output "issuer_url" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.issuer_url
}

output "jwks_binding" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.jwks_binding
}

output "jwks_url" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.jwks_url
}

output "max_clock_skew" {
  description = "returns a number"
  value       = data.okta_idp_oidc.this.max_clock_skew
}

output "protocol_type" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.protocol_type
}

output "scopes" {
  description = "returns a set of string"
  value       = data.okta_idp_oidc.this.scopes
}

output "token_binding" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.token_binding
}

output "token_url" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.token_url
}

output "type" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.type
}

output "user_info_binding" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.user_info_binding
}

output "user_info_url" {
  description = "returns a string"
  value       = data.okta_idp_oidc.this.user_info_url
}

output "this" {
  value = okta_idp_oidc.this
}
```

[top](#index)