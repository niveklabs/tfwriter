# grafana_user

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
module "grafana_user" {
  source = "./modules/grafana/r/grafana_user"

  # email - (required) is a type of string
  email = null
  # is_admin - (optional) is a type of bool
  is_admin = null
  # login - (optional) is a type of string
  login = null
  # name - (optional) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(required)"
  type        = string
}

variable "is_admin" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "login" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "grafana_user" "this" {
  # email - (required) is a type of string
  email = var.email
  # is_admin - (optional) is a type of bool
  is_admin = var.is_admin
  # login - (optional) is a type of string
  login = var.login
  # name - (optional) is a type of string
  name = var.name
  # password - (required) is a type of string
  password = var.password
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = grafana_user.this.id
}

output "this" {
  value = grafana_user.this
}
```

[top](#index)