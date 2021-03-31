# fortios_system_zone

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
module "fortios_system_zone" {
  source = "./modules/fortios/d/fortios_system_zone"

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
data "fortios_system_zone" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.fortios_system_zone.this.description
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_zone.this.id
}

output "interface" {
  description = "returns a list of object"
  value       = data.fortios_system_zone.this.interface
}

output "intrazone" {
  description = "returns a string"
  value       = data.fortios_system_zone.this.intrazone
}

output "tagging" {
  description = "returns a list of object"
  value       = data.fortios_system_zone.this.tagging
}

output "this" {
  value = fortios_system_zone.this
}
```

[top](#index)