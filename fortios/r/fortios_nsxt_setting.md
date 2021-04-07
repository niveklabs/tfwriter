# fortios_nsxt_setting

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
module "fortios_nsxt_setting" {
  source = "./modules/fortios/r/fortios_nsxt_setting"

  # liveness - (optional) is a type of string
  liveness = null
  # service - (optional) is a type of string
  service = null
}
```

[top](#index)

### Variables

```terraform
variable "liveness" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_nsxt_setting" "this" {
  # liveness - (optional) is a type of string
  liveness = var.liveness
  # service - (optional) is a type of string
  service = var.service
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_nsxt_setting.this.id
}

output "liveness" {
  description = "returns a string"
  value       = fortios_nsxt_setting.this.liveness
}

output "service" {
  description = "returns a string"
  value       = fortios_nsxt_setting.this.service
}

output "this" {
  value = fortios_nsxt_setting.this
}
```

[top](#index)