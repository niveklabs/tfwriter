# grafana_team

[back](../grafana.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    grafana = ">= 1.9.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "grafana_team" {
  source = "./modules/grafana/r/grafana_team"

  # email - (optional) is a type of string
  email = null
  # members - (optional) is a type of list of string
  members = []
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "members" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "grafana_team" "this" {
  # email - (optional) is a type of string
  email = var.email
  # members - (optional) is a type of list of string
  members = var.members
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = grafana_team.this.id
}

output "team_id" {
  description = "returns a number"
  value       = grafana_team.this.team_id
}

output "this" {
  value = grafana_team.this
}
```

[top](#index)