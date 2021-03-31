# linode_user

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/linode/d/linode_user"

  # username - (required) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "username" {
  description = "(required) - This User's username. This is used for logging in, and may also be displayed alongside actions the User performs (for example, in Events or public StackScripts)."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "linode_user" "this" {
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "email" {
  description = "returns a string"
  value       = data.linode_user.this.email
}

output "id" {
  description = "returns a string"
  value       = data.linode_user.this.id
}

output "restricted" {
  description = "returns a bool"
  value       = data.linode_user.this.restricted
}

output "ssh_keys" {
  description = "returns a list of string"
  value       = data.linode_user.this.ssh_keys
}

output "this" {
  value = linode_user.this
}
```

[top](#index)