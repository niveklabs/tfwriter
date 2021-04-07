# fortios_user_fortitoken

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
module "fortios_user_fortitoken" {
  source = "./modules/fortios/r/fortios_user_fortitoken"

  # activation_code - (optional) is a type of string
  activation_code = null
  # activation_expire - (optional) is a type of number
  activation_expire = null
  # comments - (optional) is a type of string
  comments = null
  # license - (optional) is a type of string
  license = null
  # os_ver - (optional) is a type of string
  os_ver = null
  # reg_id - (optional) is a type of string
  reg_id = null
  # seed - (optional) is a type of string
  seed = null
  # serial_number - (optional) is a type of string
  serial_number = null
  # status - (optional) is a type of string
  status = null
}
```

[top](#index)

### Variables

```terraform
variable "activation_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "activation_expire" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "license" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_ver" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reg_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "seed" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "serial_number" {
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
resource "fortios_user_fortitoken" "this" {
  # activation_code - (optional) is a type of string
  activation_code = var.activation_code
  # activation_expire - (optional) is a type of number
  activation_expire = var.activation_expire
  # comments - (optional) is a type of string
  comments = var.comments
  # license - (optional) is a type of string
  license = var.license
  # os_ver - (optional) is a type of string
  os_ver = var.os_ver
  # reg_id - (optional) is a type of string
  reg_id = var.reg_id
  # seed - (optional) is a type of string
  seed = var.seed
  # serial_number - (optional) is a type of string
  serial_number = var.serial_number
  # status - (optional) is a type of string
  status = var.status
}
```

[top](#index)

### Outputs

```terraform
output "activation_code" {
  description = "returns a string"
  value       = fortios_user_fortitoken.this.activation_code
}

output "activation_expire" {
  description = "returns a number"
  value       = fortios_user_fortitoken.this.activation_expire
}

output "id" {
  description = "returns a string"
  value       = fortios_user_fortitoken.this.id
}

output "license" {
  description = "returns a string"
  value       = fortios_user_fortitoken.this.license
}

output "os_ver" {
  description = "returns a string"
  value       = fortios_user_fortitoken.this.os_ver
}

output "reg_id" {
  description = "returns a string"
  value       = fortios_user_fortitoken.this.reg_id
}

output "seed" {
  description = "returns a string"
  value       = fortios_user_fortitoken.this.seed
}

output "serial_number" {
  description = "returns a string"
  value       = fortios_user_fortitoken.this.serial_number
}

output "status" {
  description = "returns a string"
  value       = fortios_user_fortitoken.this.status
}

output "this" {
  value = fortios_user_fortitoken.this
}
```

[top](#index)