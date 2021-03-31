# tfe_team

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
module "tfe_team" {
  source = "./modules/tfe/d/tfe_team"

  # name - (required) is a type of string
  name = null
  # organization - (required) is a type of string
  organization = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
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
data "tfe_team" "this" {
  name         = var.name
  organization = var.organization
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tfe_team.this.id
}

output "this" {
  value = tfe_team.this
}
```

[top](#index)