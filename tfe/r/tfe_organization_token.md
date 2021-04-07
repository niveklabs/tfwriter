# tfe_organization_token

[back](../tfe.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "tfe_organization_token" {
  source = "./modules/tfe/r/tfe_organization_token"

  # force_regenerate - (optional) is a type of bool
  force_regenerate = null
  # organization - (required) is a type of string
  organization = null
}
```

[top](#index)

### Variables

```terraform
variable "force_regenerate" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "organization" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tfe_organization_token" "this" {
  # force_regenerate - (optional) is a type of bool
  force_regenerate = var.force_regenerate
  # organization - (required) is a type of string
  organization = var.organization
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tfe_organization_token.this.id
}

output "token" {
  description = "returns a string"
  value       = tfe_organization_token.this.token
  sensitive   = true
}

output "this" {
  value = tfe_organization_token.this
}
```

[top](#index)