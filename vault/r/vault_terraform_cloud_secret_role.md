# vault_terraform_cloud_secret_role

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
module "vault_terraform_cloud_secret_role" {
  source = "./modules/vault/r/vault_terraform_cloud_secret_role"

  # backend - (optional) is a type of string
  backend = null
  # max_ttl - (optional) is a type of number
  max_ttl = null
  # name - (required) is a type of string
  name = null
  # organization - (optional) is a type of string
  organization = null
  # team_id - (optional) is a type of string
  team_id = null
  # ttl - (optional) is a type of number
  ttl = null
  # user_id - (optional) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "backend" {
  description = "(optional) - The path of the Terraform Cloud Secret Backend the role belongs to."
  type        = string
  default     = null
}

variable "max_ttl" {
  description = "(optional) - Maximum allowed lease for generated credentials. If not set or set to 0, will use system default."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - The name of an existing role against which to create this Terraform Cloud credential"
  type        = string
}

variable "organization" {
  description = "(optional) - Name of the Terraform Cloud or Enterprise organization"
  type        = string
  default     = null
}

variable "team_id" {
  description = "(optional) - ID of the Terraform Cloud or Enterprise team under organization (e.g., settings/teams/team-xxxxxxxxxxxxx)"
  type        = string
  default     = null
}

variable "ttl" {
  description = "(optional) - Default lease for generated credentials. If not set or set to 0, will use system default."
  type        = number
  default     = null
}

variable "user_id" {
  description = "(optional) - ID of the Terraform Cloud or Enterprise user (e.g., user-xxxxxxxxxxxxxxxx)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vault_terraform_cloud_secret_role" "this" {
  backend      = var.backend
  max_ttl      = var.max_ttl
  name         = var.name
  organization = var.organization
  team_id      = var.team_id
  ttl          = var.ttl
  user_id      = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vault_terraform_cloud_secret_role.this.id
}

output "this" {
  value = vault_terraform_cloud_secret_role.this
}
```

[top](#index)