# vault_gcp_auth_backend

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vault = ">= 2.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vault_gcp_auth_backend" {
  source = "./modules/vault/r/vault_gcp_auth_backend"

  # client_email - (optional) is a type of string
  client_email = null
  # client_id - (optional) is a type of string
  client_id = null
  # credentials - (optional) is a type of string
  credentials = null
  # description - (optional) is a type of string
  description = null
  # local - (optional) is a type of bool
  local = null
  # path - (optional) is a type of string
  path = null
  # private_key_id - (optional) is a type of string
  private_key_id = null
  # project_id - (optional) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "client_email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "credentials" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local" {
  description = "(optional) - Specifies if the auth method is local only"
  type        = bool
  default     = null
}

variable "path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_gcp_auth_backend" "this" {
  # client_email - (optional) is a type of string
  client_email = var.client_email
  # client_id - (optional) is a type of string
  client_id = var.client_id
  # credentials - (optional) is a type of string
  credentials = var.credentials
  # description - (optional) is a type of string
  description = var.description
  # local - (optional) is a type of bool
  local = var.local
  # path - (optional) is a type of string
  path = var.path
  # private_key_id - (optional) is a type of string
  private_key_id = var.private_key_id
  # project_id - (optional) is a type of string
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "client_email" {
  description = "returns a string"
  value       = vault_gcp_auth_backend.this.client_email
}

output "client_id" {
  description = "returns a string"
  value       = vault_gcp_auth_backend.this.client_id
}

output "id" {
  description = "returns a string"
  value       = vault_gcp_auth_backend.this.id
}

output "private_key_id" {
  description = "returns a string"
  value       = vault_gcp_auth_backend.this.private_key_id
}

output "project_id" {
  description = "returns a string"
  value       = vault_gcp_auth_backend.this.project_id
}

output "this" {
  value = vault_gcp_auth_backend.this
}
```

[top](#index)