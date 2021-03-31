# fortios_user_saml

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_user_saml" {
  source = "./modules/fortios/d/fortios_user_saml"

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
data "fortios_user_saml" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "cert" {
  description = "returns a string"
  value       = data.fortios_user_saml.this.cert
}

output "entity_id" {
  description = "returns a string"
  value       = data.fortios_user_saml.this.entity_id
}

output "group_name" {
  description = "returns a string"
  value       = data.fortios_user_saml.this.group_name
}

output "id" {
  description = "returns a string"
  value       = data.fortios_user_saml.this.id
}

output "idp_cert" {
  description = "returns a string"
  value       = data.fortios_user_saml.this.idp_cert
}

output "idp_entity_id" {
  description = "returns a string"
  value       = data.fortios_user_saml.this.idp_entity_id
}

output "idp_single_logout_url" {
  description = "returns a string"
  value       = data.fortios_user_saml.this.idp_single_logout_url
}

output "idp_single_sign_on_url" {
  description = "returns a string"
  value       = data.fortios_user_saml.this.idp_single_sign_on_url
}

output "single_logout_url" {
  description = "returns a string"
  value       = data.fortios_user_saml.this.single_logout_url
}

output "single_sign_on_url" {
  description = "returns a string"
  value       = data.fortios_user_saml.this.single_sign_on_url
}

output "user_name" {
  description = "returns a string"
  value       = data.fortios_user_saml.this.user_name
}

output "this" {
  value = fortios_user_saml.this
}
```

[top](#index)