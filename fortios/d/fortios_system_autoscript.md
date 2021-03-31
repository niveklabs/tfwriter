# fortios_system_autoscript

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
module "fortios_system_autoscript" {
  source = "./modules/fortios/d/fortios_system_autoscript"

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
data "fortios_system_autoscript" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.fortios_system_autoscript.this.id
}

output "interval" {
  description = "returns a number"
  value       = data.fortios_system_autoscript.this.interval
}

output "output_size" {
  description = "returns a number"
  value       = data.fortios_system_autoscript.this.output_size
}

output "repeat" {
  description = "returns a number"
  value       = data.fortios_system_autoscript.this.repeat
}

output "script" {
  description = "returns a string"
  value       = data.fortios_system_autoscript.this.script
}

output "start" {
  description = "returns a string"
  value       = data.fortios_system_autoscript.this.start
}

output "timeout" {
  description = "returns a number"
  value       = data.fortios_system_autoscript.this.timeout
}

output "this" {
  value = fortios_system_autoscript.this
}
```

[top](#index)