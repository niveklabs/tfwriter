# linode_user

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_user" {
  source = "./modules/linode/r/linode_user"

  # email - (required) is a type of string
  email = null
  # restricted - (optional) is a type of bool
  restricted = null
  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(required) - The email of the user."
  type        = string
}

variable "restricted" {
  description = "(optional) - If true, the user must be explicitly granted access to platform actions and entities."
  type        = bool
  default     = null
}

variable "username" {
  description = "(required) - The username of the user."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "linode_user" "this" {
  # email - (required) is a type of string
  email = var.email
  # restricted - (optional) is a type of bool
  restricted = var.restricted
  # username - (required) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = linode_user.this.id
}

output "ssh_keys" {
  description = "returns a list of string"
  value       = linode_user.this.ssh_keys
}

output "tfa_enabled" {
  description = "returns a bool"
  value       = linode_user.this.tfa_enabled
}

output "this" {
  value = linode_user.this
}
```

[top](#index)