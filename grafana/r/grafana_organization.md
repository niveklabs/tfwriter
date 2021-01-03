# grafana_organization

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
    grafana = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "grafana_organization" {
  source = "./modules/grafana/r/grafana_organization"

  # admin_user - (optional) is a type of string
  admin_user = null
  # admins - (optional) is a type of set of string
  admins = []
  # create_users - (optional) is a type of bool
  create_users = null
  # editors - (optional) is a type of set of string
  editors = []
  # name - (required) is a type of string
  name = null
  # viewers - (optional) is a type of set of string
  viewers = []
}
```

[top](#index)

### Variables

```terraform
variable "admin_user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admins" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "create_users" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "editors" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "viewers" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "grafana_organization" "this" {
  admin_user   = var.admin_user
  admins       = var.admins
  create_users = var.create_users
  editors      = var.editors
  name         = var.name
  viewers      = var.viewers
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = grafana_organization.this.id
}

output "org_id" {
  description = "returns a number"
  value       = grafana_organization.this.org_id
}

output "this" {
  value = grafana_organization.this
}
```

[top](#index)