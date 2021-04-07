# grafana_dashboard

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
module "grafana_dashboard" {
  source = "./modules/grafana/r/grafana_dashboard"

  # config_json - (required) is a type of string
  config_json = null
  # folder - (optional) is a type of number
  folder = null
}
```

[top](#index)

### Variables

```terraform
variable "config_json" {
  description = "(required)"
  type        = string
}

variable "folder" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "grafana_dashboard" "this" {
  # config_json - (required) is a type of string
  config_json = var.config_json
  # folder - (optional) is a type of number
  folder = var.folder
}
```

[top](#index)

### Outputs

```terraform
output "dashboard_id" {
  description = "returns a number"
  value       = grafana_dashboard.this.dashboard_id
}

output "id" {
  description = "returns a string"
  value       = grafana_dashboard.this.id
}

output "slug" {
  description = "returns a string"
  value       = grafana_dashboard.this.slug
}

output "this" {
  value = grafana_dashboard.this
}
```

[top](#index)