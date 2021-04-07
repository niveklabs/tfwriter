# okta_idp_saml

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
module "okta_idp_saml" {
  source = "./modules/okta/d/okta_idp_saml"

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
data "okta_idp_saml" "this" {
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "acs_binding" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.acs_binding
}

output "acs_type" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.acs_type
}

output "audience" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.audience
}

output "id" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.id
}

output "issuer" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.issuer
}

output "issuer_mode" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.issuer_mode
}

output "kid" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.kid
}

output "sso_binding" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.sso_binding
}

output "sso_destination" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.sso_destination
}

output "sso_url" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.sso_url
}

output "subject_filter" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.subject_filter
}

output "subject_format" {
  description = "returns a set of string"
  value       = data.okta_idp_saml.this.subject_format
}

output "type" {
  description = "returns a string"
  value       = data.okta_idp_saml.this.type
}

output "this" {
  value = okta_idp_saml.this
}
```

[top](#index)