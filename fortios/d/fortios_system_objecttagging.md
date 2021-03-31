# fortios_system_objecttagging

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
module "fortios_system_objecttagging" {
  source = "./modules/fortios/d/fortios_system_objecttagging"

  # category - (required) is a type of string
  category = null
}
```

[top](#index)

### Variables

```terraform
variable "category" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_objecttagging" "this" {
  category = var.category
}
```

[top](#index)

### Outputs

```terraform
output "address" {
  description = "returns a string"
  value       = data.fortios_system_objecttagging.this.address
}

output "color" {
  description = "returns a number"
  value       = data.fortios_system_objecttagging.this.color
}

output "device" {
  description = "returns a string"
  value       = data.fortios_system_objecttagging.this.device
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_objecttagging.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_objecttagging.this.interface
}

output "multiple" {
  description = "returns a string"
  value       = data.fortios_system_objecttagging.this.multiple
}

output "tags" {
  description = "returns a list of object"
  value       = data.fortios_system_objecttagging.this.tags
}

output "this" {
  value = fortios_system_objecttagging.this
}
```

[top](#index)