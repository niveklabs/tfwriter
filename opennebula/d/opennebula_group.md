# opennebula_group

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opennebula = ">= 0.2.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opennebula_group" {
  source = "./modules/opennebula/d/opennebula_group"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the group"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "opennebula_group" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "admins" {
  description = "returns a list of number"
  value       = data.opennebula_group.this.admins
}

output "id" {
  description = "returns a string"
  value       = data.opennebula_group.this.id
}

output "quotas" {
  description = "returns a set of object"
  value       = data.opennebula_group.this.quotas
}

output "users" {
  description = "returns a list of number"
  value       = data.opennebula_group.this.users
}

output "this" {
  value = opennebula_group.this
}
```

[top](#index)