# fortios_systemautoupdate_schedule

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
module "fortios_systemautoupdate_schedule" {
  source = "./modules/fortios/d/fortios_systemautoupdate_schedule"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_systemautoupdate_schedule" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "day" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_schedule.this.day
}

output "frequency" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_schedule.this.frequency
}

output "id" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_schedule.this.id
}

output "status" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_schedule.this.status
}

output "time" {
  description = "returns a string"
  value       = data.fortios_systemautoupdate_schedule.this.time
}

output "this" {
  value = fortios_systemautoupdate_schedule.this
}
```

[top](#index)