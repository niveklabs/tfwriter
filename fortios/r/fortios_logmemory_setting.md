# fortios_logmemory_setting

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
module "fortios_logmemory_setting" {
  source = "./modules/fortios/r/fortios_logmemory_setting"

  # diskfull - (optional) is a type of string
  diskfull = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "diskfull" {
  description = "(optional)"
  type        = string
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
resource "fortios_logmemory_setting" "this" {
  diskfull = var.diskfull
  status   = var.status
}
```

[top](#index)

### Outputs

```terraform
output "diskfull" {
  description = "returns a string"
  value       = fortios_logmemory_setting.this.diskfull
}

output "id" {
  description = "returns a string"
  value       = fortios_logmemory_setting.this.id
}

output "status" {
  description = "returns a string"
  value       = fortios_logmemory_setting.this.status
}

output "this" {
  value = fortios_logmemory_setting.this
}
```

[top](#index)