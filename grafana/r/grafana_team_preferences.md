# grafana_team_preferences

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
module "grafana_team_preferences" {
  source = "./modules/grafana/r/grafana_team_preferences"

  # home_dashboard_id - (optional) is a type of number
  home_dashboard_id = null
  # team_id - (required) is a type of number
  team_id = null
  # theme - (optional) is a type of string
  theme = null
  # timezone - (optional) is a type of string
  timezone = null
}
```

[top](#index)

### Variables

```terraform
variable "home_dashboard_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "team_id" {
  description = "(required)"
  type        = number
}

variable "theme" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "grafana_team_preferences" "this" {
  home_dashboard_id = var.home_dashboard_id
  team_id           = var.team_id
  theme             = var.theme
  timezone          = var.timezone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = grafana_team_preferences.this.id
}

output "this" {
  value = grafana_team_preferences.this
}
```

[top](#index)