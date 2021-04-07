# fortios_system_dscpbasedpriority

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
module "fortios_system_dscpbasedpriority" {
  source = "./modules/fortios/d/fortios_system_dscpbasedpriority"

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
data "fortios_system_dscpbasedpriority" "this" {
  # fosid - (required) is a type of number
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "ds" {
  description = "returns a number"
  value       = data.fortios_system_dscpbasedpriority.this.ds
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_dscpbasedpriority.this.id
}

output "priority" {
  description = "returns a string"
  value       = data.fortios_system_dscpbasedpriority.this.priority
}

output "this" {
  value = fortios_system_dscpbasedpriority.this
}
```

[top](#index)