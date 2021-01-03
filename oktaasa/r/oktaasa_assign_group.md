# oktaasa_assign_group

[back](../oktaasa.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oktaasa = ">= 1.0.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oktaasa_assign_group" {
  source = "./modules/oktaasa/r/oktaasa_assign_group"

  # create_server_group - (optional) is a type of bool
  create_server_group = null
  # group_name - (required) is a type of string
  group_name = null
  # project_name - (required) is a type of string
  project_name = null
  # server_access - (optional) is a type of bool
  server_access = null
  # server_admin - (optional) is a type of bool
  server_admin = null
}
```

[top](#index)

### Variables

```terraform
variable "create_server_group" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "group_name" {
  description = "(required)"
  type        = string
}

variable "project_name" {
  description = "(required)"
  type        = string
}

variable "server_access" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "server_admin" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "oktaasa_assign_group" "this" {
  create_server_group = var.create_server_group
  group_name          = var.group_name
  project_name        = var.project_name
  server_access       = var.server_access
  server_admin        = var.server_admin
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oktaasa_assign_group.this.id
}

output "this" {
  value = oktaasa_assign_group.this
}
```

[top](#index)