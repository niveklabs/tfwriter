# fortios_user_saml

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/fortios/r/fortios_user_saml"

  # cert - (optional) is a type of string
  cert = null
  # entity_id - (required) is a type of string
  entity_id = null
  # group_name - (optional) is a type of string
  group_name = null
  # idp_cert - (required) is a type of string
  idp_cert = null
  # idp_entity_id - (required) is a type of string
  idp_entity_id = null
  # idp_single_logout_url - (optional) is a type of string
  idp_single_logout_url = null
  # idp_single_sign_on_url - (required) is a type of string
  idp_single_sign_on_url = null
  # name - (optional) is a type of string
  name = null
  # single_logout_url - (optional) is a type of string
  single_logout_url = null
  # single_sign_on_url - (required) is a type of string
  single_sign_on_url = null
  # user_name - (optional) is a type of string
  user_name = null
}
```

[top](#index)

### Variables

```terraform
variable "cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "entity_id" {
  description = "(required)"
  type        = string
}

variable "group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idp_cert" {
  description = "(required)"
  type        = string
}

variable "idp_entity_id" {
  description = "(required)"
  type        = string
}

variable "idp_single_logout_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "idp_single_sign_on_url" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "single_logout_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "single_sign_on_url" {
  description = "(required)"
  type        = string
}

variable "user_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_user_saml" "this" {
  cert                   = var.cert
  entity_id              = var.entity_id
  group_name             = var.group_name
  idp_cert               = var.idp_cert
  idp_entity_id          = var.idp_entity_id
  idp_single_logout_url  = var.idp_single_logout_url
  idp_single_sign_on_url = var.idp_single_sign_on_url
  name                   = var.name
  single_logout_url      = var.single_logout_url
  single_sign_on_url     = var.single_sign_on_url
  user_name              = var.user_name
}
```

[top](#index)

### Outputs

```terraform
output "cert" {
  description = "returns a string"
  value       = fortios_user_saml.this.cert
}

output "group_name" {
  description = "returns a string"
  value       = fortios_user_saml.this.group_name
}

output "id" {
  description = "returns a string"
  value       = fortios_user_saml.this.id
}

output "idp_single_logout_url" {
  description = "returns a string"
  value       = fortios_user_saml.this.idp_single_logout_url
}

output "name" {
  description = "returns a string"
  value       = fortios_user_saml.this.name
}

output "single_logout_url" {
  description = "returns a string"
  value       = fortios_user_saml.this.single_logout_url
}

output "user_name" {
  description = "returns a string"
  value       = fortios_user_saml.this.user_name
}

output "this" {
  value = fortios_user_saml.this
}
```

[top](#index)