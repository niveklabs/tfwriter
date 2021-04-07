# panos_userid_login

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_userid_login" {
  source = "./modules/panos/r/panos_userid_login"

  # ip - (required) is a type of string
  ip = null
  # user - (required) is a type of string
  user = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(required) - IP address the user is logging in from"
  type        = string
}

variable "user" {
  description = "(required) - User that should be logged in"
  type        = string
}

variable "vsys" {
  description = "(optional) - The vsys to config DAG tags for"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_userid_login" "this" {
  # ip - (required) is a type of string
  ip = var.ip
  # user - (required) is a type of string
  user = var.user
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = panos_userid_login.this.id
}

output "this" {
  value = panos_userid_login.this
}
```

[top](#index)