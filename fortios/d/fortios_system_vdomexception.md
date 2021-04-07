# fortios_system_vdomexception

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
module "fortios_system_vdomexception" {
  source = "./modules/fortios/d/fortios_system_vdomexception"

  # fosid - (required) is a type of number
  fosid = null
}
```

[top](#index)

### Variables

```terraform
variable "fosid" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_vdomexception" "this" {
  # fosid - (required) is a type of number
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_vdomexception.this.id
}

output "object" {
  description = "returns a string"
  value       = data.fortios_system_vdomexception.this.object
}

output "oid" {
  description = "returns a number"
  value       = data.fortios_system_vdomexception.this.oid
}

output "scope" {
  description = "returns a string"
  value       = data.fortios_system_vdomexception.this.scope
}

output "vdom" {
  description = "returns a list of object"
  value       = data.fortios_system_vdomexception.this.vdom
}

output "this" {
  value = fortios_system_vdomexception.this
}
```

[top](#index)