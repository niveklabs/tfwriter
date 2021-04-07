# okta_group

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
module "okta_group" {
  source = "./modules/okta/d/okta_group"

  # include_users - (optional) is a type of bool
  include_users = null
  # name - (optional) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "include_users" {
  description = "(optional) - Fetch group users, having default off cuts down on API calls."
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Type of the group. When specified in the terraform resource, will act as a filter when searching for the group"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "okta_group" "this" {
  # include_users - (optional) is a type of bool
  include_users = var.include_users
  # name - (optional) is a type of string
  name = var.name
  # type - (optional) is a type of string
  type = var.type
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.okta_group.this.description
}

output "id" {
  description = "returns a string"
  value       = data.okta_group.this.id
}

output "users" {
  description = "returns a set of string"
  value       = data.okta_group.this.users
}

output "this" {
  value = okta_group.this
}
```

[top](#index)