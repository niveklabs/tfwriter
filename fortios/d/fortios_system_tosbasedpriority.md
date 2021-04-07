# fortios_system_tosbasedpriority

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
module "fortios_system_tosbasedpriority" {
  source = "./modules/fortios/d/fortios_system_tosbasedpriority"

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
data "fortios_system_tosbasedpriority" "this" {
  # fosid - (required) is a type of number
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_tosbasedpriority.this.id
}

output "priority" {
  description = "returns a string"
  value       = data.fortios_system_tosbasedpriority.this.priority
}

output "tos" {
  description = "returns a number"
  value       = data.fortios_system_tosbasedpriority.this.tos
}

output "this" {
  value = fortios_system_tosbasedpriority.this
}
```

[top](#index)