# fortios_system_networkvisibility

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
module "fortios_system_networkvisibility" {
  source = "./modules/fortios/d/fortios_system_networkvisibility"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_networkvisibility" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "destination_hostname_visibility" {
  description = "returns a string"
  value       = data.fortios_system_networkvisibility.this.destination_hostname_visibility
}

output "destination_location" {
  description = "returns a string"
  value       = data.fortios_system_networkvisibility.this.destination_location
}

output "destination_visibility" {
  description = "returns a string"
  value       = data.fortios_system_networkvisibility.this.destination_visibility
}

output "hostname_limit" {
  description = "returns a number"
  value       = data.fortios_system_networkvisibility.this.hostname_limit
}

output "hostname_ttl" {
  description = "returns a number"
  value       = data.fortios_system_networkvisibility.this.hostname_ttl
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_networkvisibility.this.id
}

output "source_location" {
  description = "returns a string"
  value       = data.fortios_system_networkvisibility.this.source_location
}

output "this" {
  value = fortios_system_networkvisibility.this
}
```

[top](#index)