# fortios_switchcontrollerinitialconfig_template

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
module "fortios_switchcontrollerinitialconfig_template" {
  source = "./modules/fortios/r/fortios_switchcontrollerinitialconfig_template"

  # allowaccess - (optional) is a type of string
  allowaccess = null
  # auto_ip - (optional) is a type of string
  auto_ip = null
  # dhcp_server - (optional) is a type of string
  dhcp_server = null
  # ip - (optional) is a type of string
  ip = null
  # name - (optional) is a type of string
  name = null
  # vlanid - (optional) is a type of number
  vlanid = null
}
```

[top](#index)

### Variables

```terraform
variable "allowaccess" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dhcp_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlanid" {
  description = "(optional)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_switchcontrollerinitialconfig_template" "this" {
  # allowaccess - (optional) is a type of string
  allowaccess = var.allowaccess
  # auto_ip - (optional) is a type of string
  auto_ip = var.auto_ip
  # dhcp_server - (optional) is a type of string
  dhcp_server = var.dhcp_server
  # ip - (optional) is a type of string
  ip = var.ip
  # name - (optional) is a type of string
  name = var.name
  # vlanid - (optional) is a type of number
  vlanid = var.vlanid
}
```

[top](#index)

### Outputs

```terraform
output "allowaccess" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_template.this.allowaccess
}

output "auto_ip" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_template.this.auto_ip
}

output "dhcp_server" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_template.this.dhcp_server
}

output "id" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_template.this.id
}

output "ip" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_template.this.ip
}

output "name" {
  description = "returns a string"
  value       = fortios_switchcontrollerinitialconfig_template.this.name
}

output "vlanid" {
  description = "returns a number"
  value       = fortios_switchcontrollerinitialconfig_template.this.vlanid
}

output "this" {
  value = fortios_switchcontrollerinitialconfig_template.this
}
```

[top](#index)