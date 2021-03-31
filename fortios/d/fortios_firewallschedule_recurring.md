# fortios_firewallschedule_recurring

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
module "fortios_firewallschedule_recurring" {
  source = "./modules/fortios/d/fortios_firewallschedule_recurring"

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
data "fortios_firewallschedule_recurring" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "color" {
  description = "returns a number"
  value       = data.fortios_firewallschedule_recurring.this.color
}

output "day" {
  description = "returns a string"
  value       = data.fortios_firewallschedule_recurring.this.day
}

output "end" {
  description = "returns a string"
  value       = data.fortios_firewallschedule_recurring.this.end
}

output "id" {
  description = "returns a string"
  value       = data.fortios_firewallschedule_recurring.this.id
}

output "start" {
  description = "returns a string"
  value       = data.fortios_firewallschedule_recurring.this.start
}

output "this" {
  value = fortios_firewallschedule_recurring.this
}
```

[top](#index)