# fortios_system_arptable

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
module "fortios_system_arptable" {
  source = "./modules/fortios/d/fortios_system_arptable"

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
data "fortios_system_arptable" "this" {
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_arptable.this.id
}

output "interface" {
  description = "returns a string"
  value       = data.fortios_system_arptable.this.interface
}

output "ip" {
  description = "returns a string"
  value       = data.fortios_system_arptable.this.ip
}

output "mac" {
  description = "returns a string"
  value       = data.fortios_system_arptable.this.mac
}

output "this" {
  value = fortios_system_arptable.this
}
```

[top](#index)