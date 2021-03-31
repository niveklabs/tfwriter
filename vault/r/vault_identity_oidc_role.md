# vault_identity_oidc_role

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
module "vault_identity_oidc_role" {
  source = "./modules/vault/r/vault_identity_oidc_role"

  # client_id - (optional) is a type of string
  client_id = null
  # key - (required) is a type of string
  key = null
  # name - (required) is a type of string
  name = null
  # template - (optional) is a type of string
  template = null
  # ttl - (optional) is a type of number
  ttl = null
}
```

[top](#index)

### Variables

```terraform
variable "client_id" {
  description = "(optional) - The value that will be included in the `aud` field of all the OIDC identity tokens issued by this role"
  type        = string
  default     = null
}

variable "key" {
  description = "(required) - A configured named key, the key must already exist."
  type        = string
}

variable "name" {
  description = "(required) - Name of the role."
  type        = string
}

variable "template" {
  description = "(optional) - The template string to use for generating tokens. This may be in string-ified JSON or base64 format."
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional) - TTL of the tokens generated against the role in number of seconds."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_identity_oidc_role" "this" {
  client_id = var.client_id
  key       = var.key
  name      = var.name
  template  = var.template
  ttl       = var.ttl
}
```

[top](#index)

### Outputs

```terraform
output "client_id" {
  description = "returns a string"
  value       = vault_identity_oidc_role.this.client_id
}

output "id" {
  description = "returns a string"
  value       = vault_identity_oidc_role.this.id
}

output "this" {
  value = vault_identity_oidc_role.this
}
```

[top](#index)