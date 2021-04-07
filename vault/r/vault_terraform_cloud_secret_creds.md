# vault_terraform_cloud_secret_creds

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
module "vault_terraform_cloud_secret_creds" {
  source = "./modules/vault/r/vault_terraform_cloud_secret_creds"

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
  description = "(required) - Terraform Cloud secret backend to generate tokens from"
  type        = string
}

variable "role" {
  description = "(required) - Name of the role."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "vault_terraform_cloud_secret_creds" "this" {
  # backend - (required) is a type of string
  backend = var.backend
  # role - (required) is a type of string
  role = var.role
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_terraform_cloud_secret_creds.this.id
}

output "lease_id" {
  description = "returns a string"
  value       = vault_terraform_cloud_secret_creds.this.lease_id
  sensitive   = true
}

output "organization" {
  description = "returns a string"
  value       = vault_terraform_cloud_secret_creds.this.organization
}

output "team_id" {
  description = "returns a string"
  value       = vault_terraform_cloud_secret_creds.this.team_id
}

output "token" {
  description = "returns a string"
  value       = vault_terraform_cloud_secret_creds.this.token
  sensitive   = true
}

output "token_id" {
  description = "returns a string"
  value       = vault_terraform_cloud_secret_creds.this.token_id
}

output "this" {
  value = vault_terraform_cloud_secret_creds.this
}
```

[top](#index)