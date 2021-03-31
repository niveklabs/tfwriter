# fortios_system_automationdestination

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
module "fortios_system_automationdestination" {
  source = "./modules/fortios/d/fortios_system_automationdestination"

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
data "fortios_system_automationdestination" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "destination" {
  description = "returns a list of object"
  value       = data.fortios_system_automationdestination.this.destination
}

output "ha_group_id" {
  description = "returns a number"
  value       = data.fortios_system_automationdestination.this.ha_group_id
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_automationdestination.this.id
}

output "type" {
  description = "returns a string"
  value       = data.fortios_system_automationdestination.this.type
}

output "this" {
  value = fortios_system_automationdestination.this
}
```

[top](#index)