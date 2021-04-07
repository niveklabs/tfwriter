# tfe_organization_membership

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tfe = ">= 0.24.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tfe_organization_membership" {
  source = "./modules/tfe/d/tfe_organization_membership"

  # email - (required) is a type of string
  email = null
  # organization - (required) is a type of string
  organization = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(required)"
  type        = string
}

variable "organization" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tfe_organization_membership" "this" {
  # email - (required) is a type of string
  email = var.email
  # organization - (required) is a type of string
  organization = var.organization
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tfe_organization_membership.this.id
}

output "user_id" {
  description = "returns a string"
  value       = data.tfe_organization_membership.this.user_id
}

output "this" {
  value = tfe_organization_membership.this
}
```

[top](#index)