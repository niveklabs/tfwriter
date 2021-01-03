# fortios_firewallipmacbinding_setting

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_firewallipmacbinding_setting" {
  source = "./modules/fortios/r/fortios_firewallipmacbinding_setting"

  # bindthroughfw - (optional) is a type of string
  bindthroughfw = null
  # bindtofw - (optional) is a type of string
  bindtofw = null
  # undefinedhost - (optional) is a type of string
  undefinedhost = null
}
```

[top](#index)

### Variables

```terraform
variable "bindthroughfw" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bindtofw" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "undefinedhost" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewallipmacbinding_setting" "this" {
  bindthroughfw = var.bindthroughfw
  bindtofw      = var.bindtofw
  undefinedhost = var.undefinedhost
}
```

[top](#index)

### Outputs

```terraform
output "bindthroughfw" {
  description = "returns a string"
  value       = fortios_firewallipmacbinding_setting.this.bindthroughfw
}

output "bindtofw" {
  description = "returns a string"
  value       = fortios_firewallipmacbinding_setting.this.bindtofw
}

output "id" {
  description = "returns a string"
  value       = fortios_firewallipmacbinding_setting.this.id
}

output "undefinedhost" {
  description = "returns a string"
  value       = fortios_firewallipmacbinding_setting.this.undefinedhost
}

output "this" {
  value = fortios_firewallipmacbinding_setting.this
}
```

[top](#index)