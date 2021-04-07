# fortios_system_fipscc

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/fortios/r/fortios_system_fipscc"

  # entropy_token - (optional) is a type of string
  entropy_token = null
  # key_generation_self_test - (optional) is a type of string
  key_generation_self_test = null
  # self_test_period - (optional) is a type of number
  self_test_period = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "entropy_token" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_generation_self_test" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "self_test_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_fipscc" "this" {
  # entropy_token - (optional) is a type of string
  entropy_token = var.entropy_token
  # key_generation_self_test - (optional) is a type of string
  key_generation_self_test = var.key_generation_self_test
  # self_test_period - (optional) is a type of number
  self_test_period = var.self_test_period
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "entropy_token" {
  description = "returns a string"
  value       = fortios_system_fipscc.this.entropy_token
}

output "id" {
  description = "returns a string"
  value       = fortios_system_fipscc.this.id
}

output "key_generation_self_test" {
  description = "returns a string"
  value       = fortios_system_fipscc.this.key_generation_self_test
}

output "self_test_period" {
  description = "returns a number"
  value       = fortios_system_fipscc.this.self_test_period
}

output "status" {
  description = "returns a string"
  value       = fortios_system_fipscc.this.status
}

output "this" {
  value = fortios_system_fipscc.this
}
```

[top](#index)