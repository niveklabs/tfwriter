# fortios_switchcontrollerautoconfig_default

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
module "fortios_switchcontrollerautoconfig_default" {
  source = "./modules/fortios/r/fortios_switchcontrollerautoconfig_default"

  # fgt_policy - (optional) is a type of string
  fgt_policy = null
  # icl_policy - (optional) is a type of string
  icl_policy = null
  # isl_policy - (optional) is a type of string
  isl_policy = null
}
```

[top](#index)

### Variables

```terraform
variable "fgt_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icl_policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isl_policy" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerautoconfig_default" "this" {
  fgt_policy = var.fgt_policy
  icl_policy = var.icl_policy
  isl_policy = var.isl_policy
}
```

[top](#index)

### Outputs

```terraform
output "fgt_policy" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_default.this.fgt_policy
}

output "icl_policy" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_default.this.icl_policy
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_default.this.id
}

output "isl_policy" {
  description = "returns a string"
  value       = fortios_switchcontrollerautoconfig_default.this.isl_policy
}

output "this" {
  value = fortios_switchcontrollerautoconfig_default.this
}
```

[top](#index)