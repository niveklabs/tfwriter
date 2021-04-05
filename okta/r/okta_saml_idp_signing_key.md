# okta_saml_idp_signing_key

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
module "okta_saml_idp_signing_key" {
  source = "./modules/okta/r/okta_saml_idp_signing_key"

  # x5c - (required) is a type of set of string
  x5c = []
}
```

[top](#index)

### Variables

```terraform
variable "x5c" {
  description = "(required) - base64-encoded X.509 certificate chain with DER encoding"
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "okta_saml_idp_signing_key" "this" {
  x5c = var.x5c
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = okta_saml_idp_signing_key.this.created
}

output "expires_at" {
  description = "returns a string"
  value       = okta_saml_idp_signing_key.this.expires_at
}

output "id" {
  description = "returns a string"
  value       = okta_saml_idp_signing_key.this.id
}

output "kid" {
  description = "returns a string"
  value       = okta_saml_idp_signing_key.this.kid
}

output "kty" {
  description = "returns a string"
  value       = okta_saml_idp_signing_key.this.kty
}

output "use" {
  description = "returns a string"
  value       = okta_saml_idp_signing_key.this.use
}

output "x5t_s256" {
  description = "returns a string"
  value       = okta_saml_idp_signing_key.this.x5t_s256
}

output "this" {
  value = okta_saml_idp_signing_key.this
}
```

[top](#index)