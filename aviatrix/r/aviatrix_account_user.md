# aviatrix_account_user

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_account_user" {
  source = "./modules/aviatrix/r/aviatrix_account_user"

  # email - (required) is a type of string
  email = null
  # password - (required) is a type of string
  password = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(required) - Email of address of account user to be created."
  type        = string
}

variable "password" {
  description = "(required) - Login password for the account user to be created."
  type        = string
}

variable "username" {
  description = "(required) - Name of account user to be created. It can only include alphanumeric characters(lower case only), hyphens, dots or underscores. 1 to 80 in length. No spaces are allowed."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_account_user" "this" {
  email    = var.email
  password = var.password
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_account_user.this.id
}

output "this" {
  value = aviatrix_account_user.this
}
```

[top](#index)