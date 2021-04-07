# fortios_system_admin_administrator

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
module "fortios_system_admin_administrator" {
  source = "./modules/fortios/r/fortios_system_admin_administrator"

  # accprofile - (required) is a type of string
  accprofile = null
  # comments - (optional) is a type of string
  comments = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # trusthost1 - (optional) is a type of string
  trusthost1 = null
  # trusthost10 - (optional) is a type of string
  trusthost10 = null
  # trusthost2 - (optional) is a type of string
  trusthost2 = null
  # trusthost3 - (optional) is a type of string
  trusthost3 = null
  # trusthost4 - (optional) is a type of string
  trusthost4 = null
  # trusthost5 - (optional) is a type of string
  trusthost5 = null
  # trusthost6 - (optional) is a type of string
  trusthost6 = null
  # trusthost7 - (optional) is a type of string
  trusthost7 = null
  # trusthost8 - (optional) is a type of string
  trusthost8 = null
  # trusthost9 - (optional) is a type of string
  trusthost9 = null
  # vdom - (optional) is a type of list of string
  vdom = []
}
```

[top](#index)

### Variables

```terraform
variable "accprofile" {
  description = "(required)"
  type        = string
}

variable "comments" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "trusthost1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost10" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost5" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost7" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost8" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "trusthost9" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdom" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_admin_administrator" "this" {
  # accprofile - (required) is a type of string
  accprofile = var.accprofile
  # comments - (optional) is a type of string
  comments = var.comments
  # name - (required) is a type of string
  name = var.name
  # password - (required) is a type of string
  password = var.password
  # trusthost1 - (optional) is a type of string
  trusthost1 = var.trusthost1
  # trusthost10 - (optional) is a type of string
  trusthost10 = var.trusthost10
  # trusthost2 - (optional) is a type of string
  trusthost2 = var.trusthost2
  # trusthost3 - (optional) is a type of string
  trusthost3 = var.trusthost3
  # trusthost4 - (optional) is a type of string
  trusthost4 = var.trusthost4
  # trusthost5 - (optional) is a type of string
  trusthost5 = var.trusthost5
  # trusthost6 - (optional) is a type of string
  trusthost6 = var.trusthost6
  # trusthost7 - (optional) is a type of string
  trusthost7 = var.trusthost7
  # trusthost8 - (optional) is a type of string
  trusthost8 = var.trusthost8
  # trusthost9 - (optional) is a type of string
  trusthost9 = var.trusthost9
  # vdom - (optional) is a type of list of string
  vdom = var.vdom
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_system_admin_administrator.this.id
}

output "trusthost1" {
  description = "returns a string"
  value       = fortios_system_admin_administrator.this.trusthost1
}

output "trusthost10" {
  description = "returns a string"
  value       = fortios_system_admin_administrator.this.trusthost10
}

output "trusthost2" {
  description = "returns a string"
  value       = fortios_system_admin_administrator.this.trusthost2
}

output "trusthost3" {
  description = "returns a string"
  value       = fortios_system_admin_administrator.this.trusthost3
}

output "trusthost4" {
  description = "returns a string"
  value       = fortios_system_admin_administrator.this.trusthost4
}

output "trusthost5" {
  description = "returns a string"
  value       = fortios_system_admin_administrator.this.trusthost5
}

output "trusthost6" {
  description = "returns a string"
  value       = fortios_system_admin_administrator.this.trusthost6
}

output "trusthost7" {
  description = "returns a string"
  value       = fortios_system_admin_administrator.this.trusthost7
}

output "trusthost8" {
  description = "returns a string"
  value       = fortios_system_admin_administrator.this.trusthost8
}

output "trusthost9" {
  description = "returns a string"
  value       = fortios_system_admin_administrator.this.trusthost9
}

output "vdom" {
  description = "returns a list of string"
  value       = fortios_system_admin_administrator.this.vdom
}

output "this" {
  value = fortios_system_admin_administrator.this
}
```

[top](#index)