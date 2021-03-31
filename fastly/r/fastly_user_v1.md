# fastly_user_v1

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_user_v1" {
  source = "./modules/fastly/r/fastly_user_v1"

  # login - (required) is a type of string
  login = null
  # name - (required) is a type of string
  name = null
  # role - (optional) is a type of string
  role = null
}
```

[top](#index)

### Variables

```terraform
variable "login" {
  description = "(required) - The email address, which is the login name, of the User"
  type        = string
}

variable "name" {
  description = "(required) - The real life name of the user"
  type        = string
}

variable "role" {
  description = "(optional) - The role of this user. Can be `user` (the default), `billing`, `engineer`, or `superuser`. For detailed information on the abilities granted to each role, see [Fastly's Documentation on User roles](https://docs.fastly.com/en/guides/configuring-user-roles-and-permissions#user-roles-and-what-they-can-do)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fastly_user_v1" "this" {
  login = var.login
  name  = var.name
  role  = var.role
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fastly_user_v1.this.id
}

output "this" {
  value = fastly_user_v1.this
}
```

[top](#index)