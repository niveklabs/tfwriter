# panos_user_tag

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "panos_user_tag" {
  source = "./modules/panos/d/panos_user_tag"

  # user - (optional) is a type of string
  user = null
  # vsys - (optional) is a type of string
  vsys = null
}
```

[top](#index)

### Variables

```terraform
variable "user" {
  description = "(optional) - Filter on just this user"
  type        = string
  default     = null
}

variable "vsys" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "panos_user_tag" "this" {
  # user - (optional) is a type of string
  user = var.user
  # vsys - (optional) is a type of string
  vsys = var.vsys
}
```

[top](#index)

### Outputs

```terraform
output "entries" {
  description = "returns a list of object"
  value       = data.panos_user_tag.this.entries
}

output "id" {
  description = "returns a string"
  value       = data.panos_user_tag.this.id
}

output "this" {
  value = panos_user_tag.this
}
```

[top](#index)