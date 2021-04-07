# pagerduty_team

[back](../pagerduty.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    pagerduty = ">= 1.9.6"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "pagerduty_team" {
  source = "./modules/pagerduty/d/pagerduty_team"

  # name - (required) is a type of string
  name = null
  # parent - (optional) is a type of string
  parent = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - The name of the team to find in the PagerDuty API"
  type        = string
}

variable "parent" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "pagerduty_team" "this" {
  # name - (required) is a type of string
  name = var.name
  # parent - (optional) is a type of string
  parent = var.parent
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.pagerduty_team.this.description
}

output "id" {
  description = "returns a string"
  value       = data.pagerduty_team.this.id
}

output "this" {
  value = pagerduty_team.this
}
```

[top](#index)