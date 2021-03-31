# vault_ad_access_credentials

[back](../vault.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "vault_ad_access_credentials" {
  source = "./modules/vault/d/vault_ad_access_credentials"

  # backend - (required) is a type of string
  backend = null
  # role - (required) is a type of string
  role = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(required) - AD Secret Backend to read credentials from."
  type        = string
}

variable "role" {
  description = "(required) - Name of the role."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vault_ad_access_credentials" "this" {
  backend = var.backend
  role    = var.role
}
```

[top](#index)

### Outputs

```terraform
output "current_password" {
  description = "returns a string"
  value       = data.vault_ad_access_credentials.this.current_password
}

output "id" {
  description = "returns a string"
  value       = data.vault_ad_access_credentials.this.id
}

output "last_password" {
  description = "returns a string"
  value       = data.vault_ad_access_credentials.this.last_password
}

output "username" {
  description = "returns a string"
  value       = data.vault_ad_access_credentials.this.username
}

output "this" {
  value = vault_ad_access_credentials.this
}
```

[top](#index)