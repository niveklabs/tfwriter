# fortios_system_passwordpolicy

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
module "fortios_system_passwordpolicy" {
  source = "./modules/fortios/d/fortios_system_passwordpolicy"

}
```

[top](#index)

### Variables

```terraform
```

[top](#index)

### Datasource

```terraform
data "fortios_system_passwordpolicy" "this" {
}
```

[top](#index)

### Outputs

```terraform
output "apply_to" {
  description = "returns a string"
  value       = data.fortios_system_passwordpolicy.this.apply_to
}

output "change_4_characters" {
  description = "returns a string"
  value       = data.fortios_system_passwordpolicy.this.change_4_characters
}

output "expire_day" {
  description = "returns a number"
  value       = data.fortios_system_passwordpolicy.this.expire_day
}

output "expire_status" {
  description = "returns a string"
  value       = data.fortios_system_passwordpolicy.this.expire_status
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_passwordpolicy.this.id
}

output "min_lower_case_letter" {
  description = "returns a number"
  value       = data.fortios_system_passwordpolicy.this.min_lower_case_letter
}

output "min_non_alphanumeric" {
  description = "returns a number"
  value       = data.fortios_system_passwordpolicy.this.min_non_alphanumeric
}

output "min_number" {
  description = "returns a number"
  value       = data.fortios_system_passwordpolicy.this.min_number
}

output "min_upper_case_letter" {
  description = "returns a number"
  value       = data.fortios_system_passwordpolicy.this.min_upper_case_letter
}

output "minimum_length" {
  description = "returns a number"
  value       = data.fortios_system_passwordpolicy.this.minimum_length
}

output "reuse_password" {
  description = "returns a string"
  value       = data.fortios_system_passwordpolicy.this.reuse_password
}

output "status" {
  description = "returns a string"
  value       = data.fortios_system_passwordpolicy.this.status
}

output "this" {
  value = fortios_system_passwordpolicy.this
}
```

[top](#index)