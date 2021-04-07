# okta_app

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    okta = ">= 3.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "okta_app" {
  source = "./modules/okta/d/okta_app"

  # active_only - (optional) is a type of bool
  active_only = null
  # groups - (optional) is a type of set of string
  groups = []
  # label - (optional) is a type of string
  label = null
  # label_prefix - (optional) is a type of string
  label_prefix = null
  # users - (optional) is a type of set of string
  users = []
}
```

[top](#index)

### Variables

```terraform
variable "active_only" {
  description = "(optional) - Search only ACTIVE applications."
  type        = bool
  default     = null
}

variable "groups" {
  description = "(optional) - Groups associated with the application"
  type        = set(string)
  default     = null
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "users" {
  description = "(optional) - Users associated with the application"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "okta_app" "this" {
  # active_only - (optional) is a type of bool
  active_only = var.active_only
  # groups - (optional) is a type of set of string
  groups = var.groups
  # label - (optional) is a type of string
  label = var.label
  # label_prefix - (optional) is a type of string
  label_prefix = var.label_prefix
  # users - (optional) is a type of set of string
  users = var.users
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.okta_app.this.id
}

output "links" {
  description = "returns a string"
  value       = data.okta_app.this.links
}

output "name" {
  description = "returns a string"
  value       = data.okta_app.this.name
}

output "status" {
  description = "returns a string"
  value       = data.okta_app.this.status
}

output "this" {
  value = okta_app.this
}
```

[top](#index)