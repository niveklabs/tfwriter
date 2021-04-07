# fortios_system_alias

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_system_alias" {
  source = "./modules/fortios/d/fortios_system_alias"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_alias" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "command" {
  description = "returns a string"
  value       = data.fortios_system_alias.this.command
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_alias.this.id
}

output "this" {
  value = fortios_system_alias.this
}
```

[top](#index)