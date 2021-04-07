# icinga2_user

[back](../icinga2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    icinga2 = ">= 0.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "icinga2_user" {
  source = "./modules/icinga2/r/icinga2_user"

  # email - (optional) is a type of string
  email = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Username"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "icinga2_user" "this" {
  # email - (optional) is a type of string
  email = var.email
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = icinga2_user.this.id
}

output "this" {
  value = icinga2_user.this
}
```

[top](#index)