# fortios_system_fipscc

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
module "fortios_system_fipscc" {
  source = "./modules/fortios/d/fortios_system_fipscc"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_fipscc" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "entropy_token" {
  description = "returns a string"
  value       = data.fortios_system_fipscc.this.entropy_token
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_fipscc.this.id
}

output "key_generation_self_test" {
  description = "returns a string"
  value       = data.fortios_system_fipscc.this.key_generation_self_test
}

output "self_test_period" {
  description = "returns a number"
  value       = data.fortios_system_fipscc.this.self_test_period
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_fipscc.this.status
}

output "this" {
  value = fortios_system_fipscc.this
}
```

[top](#index)