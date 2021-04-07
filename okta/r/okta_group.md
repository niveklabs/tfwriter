# okta_group

[back](../okta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "okta_group" {
  source = "./modules/okta/r/okta_group"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # users - (optional) is a type of set of string
  users = []
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Group description"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Group name"
  type        = string
}

variable "users" {
  description = "(optional) - Users associated with the group. This can also be done per user."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "okta_group" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # users - (optional) is a type of set of string
  users = var.users
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = okta_group.this.id
}

output "this" {
  value = okta_group.this
}
```

[top](#index)