# mso_role

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_role" {
  source = "./modules/mso/d/mso_role"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # name - (required) is a type of string
  name = null
  # read_permissions - (optional) is a type of list of string
  read_permissions = []
  # write_permissions - (optional) is a type of list of string
  write_permissions = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "read_permissions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "write_permissions" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "mso_role" "this" {
  description       = var.description
  display_name      = var.display_name
  name              = var.name
  read_permissions  = var.read_permissions
  write_permissions = var.write_permissions
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.mso_role.this.description
}

output "id" {
  description = "returns a string"
  value       = data.mso_role.this.id
}

output "read_permissions" {
  description = "returns a list of string"
  value       = data.mso_role.this.read_permissions
}

output "write_permissions" {
  description = "returns a list of string"
  value       = data.mso_role.this.write_permissions
}

output "this" {
  value = mso_role.this
}
```

[top](#index)