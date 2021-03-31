# tfe_workspace_ids

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
module "tfe_workspace_ids" {
  source = "./modules/tfe/d/tfe_workspace_ids"

  # names - (required) is a type of list of string
  names = []
  # organization - (required) is a type of string
  organization = null
}
```

[top](#index)

### Variables

```terraform
variable "names" {
  description = "(required)"
  type        = list(string)
}

variable "organization" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tfe_workspace_ids" "this" {
  names        = var.names
  organization = var.organization
}
```

[top](#index)

### Outputs

```terraform
output "external_ids" {
  description = "returns a map of string"
  value       = data.tfe_workspace_ids.this.external_ids
}

output "full_names" {
  description = "returns a map of string"
  value       = data.tfe_workspace_ids.this.full_names
}

output "id" {
  description = "returns a string"
  value       = data.tfe_workspace_ids.this.id
}

output "ids" {
  description = "returns a map of string"
  value       = data.tfe_workspace_ids.this.ids
}

output "this" {
  value = tfe_workspace_ids.this
}
```

[top](#index)