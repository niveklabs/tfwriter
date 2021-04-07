# fortios_endpointcontrol_registeredforticlient

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
module "fortios_endpointcontrol_registeredforticlient" {
  source = "./modules/fortios/r/fortios_endpointcontrol_registeredforticlient"

  # flag - (optional) is a type of number
  flag = null
  # ip - (optional) is a type of string
  ip = null
  # mac - (optional) is a type of string
  mac = null
  # reg_fortigate - (optional) is a type of string
  reg_fortigate = null
  # status - (optional) is a type of number
  status = null
  # uid - (optional) is a type of string
  uid = null
  # vdom - (optional) is a type of string
  vdom = null
}
```

[top](#index)

### Variables

```terraform
variable "flag" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mac" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "reg_fortigate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdom" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_endpointcontrol_registeredforticlient" "this" {
  # flag - (optional) is a type of number
  flag = var.flag
  # ip - (optional) is a type of string
  ip = var.ip
  # mac - (optional) is a type of string
  mac = var.mac
  # reg_fortigate - (optional) is a type of string
  reg_fortigate = var.reg_fortigate
  # status - (optional) is a type of number
  status = var.status
  # uid - (optional) is a type of string
  uid = var.uid
  # vdom - (optional) is a type of string
  vdom = var.vdom
}
```

[top](#index)

### Outputs

```terraform
output "flag" {
  description = "returns a number"
  value       = fortios_endpointcontrol_registeredforticlient.this.flag
}

output "id" {
  description = "returns a string"
  value       = fortios_endpointcontrol_registeredforticlient.this.id
}

output "ip" {
  description = "returns a string"
  value       = fortios_endpointcontrol_registeredforticlient.this.ip
}

output "mac" {
  description = "returns a string"
  value       = fortios_endpointcontrol_registeredforticlient.this.mac
}

output "reg_fortigate" {
  description = "returns a string"
  value       = fortios_endpointcontrol_registeredforticlient.this.reg_fortigate
}

output "status" {
  description = "returns a number"
  value       = fortios_endpointcontrol_registeredforticlient.this.status
}

output "uid" {
  description = "returns a string"
  value       = fortios_endpointcontrol_registeredforticlient.this.uid
}

output "vdom" {
  description = "returns a string"
  value       = fortios_endpointcontrol_registeredforticlient.this.vdom
}

output "this" {
  value = fortios_endpointcontrol_registeredforticlient.this
}
```

[top](#index)