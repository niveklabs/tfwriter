# mso_user

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
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_user" {
  source = "./modules/mso/d/mso_user"

  # account_status - (optional) is a type of string
  account_status = null
  # domain - (optional) is a type of string
  domain = null
  # email - (optional) is a type of string
  email = null
  # first_name - (optional) is a type of string
  first_name = null
  # last_name - (optional) is a type of string
  last_name = null
  # phone - (optional) is a type of string
  phone = null
  # user_password - (optional) is a type of string
  user_password = null
  # username - (required) is a type of string
  username = null

  roles = [{
    access_type = null
    roleid      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "first_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "last_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "phone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(required)"
  type        = string
}

variable "roles" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access_type = string
      roleid      = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "mso_user" "this" {
  account_status = var.account_status
  domain         = var.domain
  email          = var.email
  first_name     = var.first_name
  last_name      = var.last_name
  phone          = var.phone
  user_password  = var.user_password
  username       = var.username

  dynamic "roles" {
    for_each = var.roles
    content {
      access_type = roles.value["access_type"]
      roleid      = roles.value["roleid"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.mso_user.this.id
}

output "this" {
  value = mso_user.this
}
```

[top](#index)