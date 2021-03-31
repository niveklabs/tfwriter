# fortios_system_sessionhelper

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
module "fortios_system_sessionhelper" {
  source = "./modules/fortios/d/fortios_system_sessionhelper"

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
data "fortios_system_sessionhelper" "this" {
  fosid = var.fosid
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_sessionhelper.this.id
}

output "name" {
  description = "returns a string"
  value       = data.fortios_system_sessionhelper.this.name
}

output "port" {
  description = "returns a number"
  value       = data.fortios_system_sessionhelper.this.port
}

output "protocol" {
  description = "returns a number"
  value       = data.fortios_system_sessionhelper.this.protocol
}

output "this" {
  value = fortios_system_sessionhelper.this
}
```

[top](#index)