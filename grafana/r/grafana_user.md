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
    grafana = ">= 1.8.1"
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
  email    = var.email
  login    = var.login
  name     = var.name
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