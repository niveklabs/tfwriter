# github_team

[back](../github.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    github = ">= 4.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "github_team" {
  source = "./modules/github/r/github_team"

  # description - (optional) is a type of string
  description = null
  # ldap_dn - (optional) is a type of string
  ldap_dn = null
  # name - (required) is a type of string
  name = null
  # parent_team_id - (optional) is a type of number
  parent_team_id = null
  # privacy - (optional) is a type of string
  privacy = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ldap_dn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "parent_team_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "privacy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "github_team" "this" {
  description    = var.description
  ldap_dn        = var.ldap_dn
  name           = var.name
  parent_team_id = var.parent_team_id
  privacy        = var.privacy
}
```

[top](#index)

### Outputs

```terraform
output "etag" {
  description = "returns a string"
  value       = github_team.this.etag
}

output "id" {
  description = "returns a string"
  value       = github_team.this.id
}

output "node_id" {
  description = "returns a string"
  value       = github_team.this.node_id
}

output "slug" {
  description = "returns a string"
  value       = github_team.this.slug
}

output "this" {
  value = github_team.this
}
```

[top](#index)