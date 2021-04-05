# sumologic_user

[back](../sumologic.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sumologic = ">= 2.9.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sumologic_user" {
  source = "./modules/sumologic/r/sumologic_user"

  # email - (required) is a type of string
  email = null
  # first_name - (required) is a type of string
  first_name = null
  # is_active - (required) is a type of bool
  is_active = null
  # last_name - (required) is a type of string
  last_name = null
  # role_ids - (required) is a type of list of string
  role_ids = []
  # transfer_to - (required) is a type of string
  transfer_to = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(required)"
  type        = string
}

variable "first_name" {
  description = "(required)"
  type        = string
}

variable "is_active" {
  description = "(required)"
  type        = bool
}

variable "last_name" {
  description = "(required)"
  type        = string
}

variable "role_ids" {
  description = "(required)"
  type        = list(string)
}

variable "transfer_to" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "sumologic_user" "this" {
  email       = var.email
  first_name  = var.first_name
  is_active   = var.is_active
  last_name   = var.last_name
  role_ids    = var.role_ids
  transfer_to = var.transfer_to
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = sumologic_user.this.id
}

output "this" {
  value = sumologic_user.this
}
```

[top](#index)