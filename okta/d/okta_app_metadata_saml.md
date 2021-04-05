# okta_app_metadata_saml

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
module "okta_app_metadata_saml" {
  source = "./modules/okta/d/okta_app_metadata_saml"

  # app_id - (required) is a type of string
  app_id = null
  # key_id - (optional) is a type of string
  key_id = null
}
```

[top](#index)

### Variables

```terraform
variable "app_id" {
  description = "(required)"
  type        = string
}

variable "key_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "okta_app_metadata_saml" "this" {
  app_id = var.app_id
  key_id = var.key_id
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = data.okta_app_metadata_saml.this.certificate
}

output "entity_id" {
  description = "returns a string"
  value       = data.okta_app_metadata_saml.this.entity_id
}

output "http_post_binding" {
  description = "returns a string"
  value       = data.okta_app_metadata_saml.this.http_post_binding
}

output "http_redirect_binding" {
  description = "returns a string"
  value       = data.okta_app_metadata_saml.this.http_redirect_binding
}

output "id" {
  description = "returns a string"
  value       = data.okta_app_metadata_saml.this.id
}

output "metadata" {
  description = "returns a string"
  value       = data.okta_app_metadata_saml.this.metadata
}

output "want_authn_requests_signed" {
  description = "returns a bool"
  value       = data.okta_app_metadata_saml.this.want_authn_requests_signed
}

output "this" {
  value = okta_app_metadata_saml.this
}
```

[top](#index)