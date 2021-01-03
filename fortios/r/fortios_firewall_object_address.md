# fortios_firewall_object_address

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
module "fortios_firewall_object_address" {
  source = "./modules/fortios/r/fortios_firewall_object_address"

  # associated_interface - (optional) is a type of string
  associated_interface = null
  # comment - (optional) is a type of string
  comment = null
  # country - (optional) is a type of string
  country = null
  # end_ip - (optional) is a type of string
  end_ip = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # name - (required) is a type of string
  name = null
  # show_in_address_list - (optional) is a type of string
  show_in_address_list = null
  # start_ip - (optional) is a type of string
  start_ip = null
  # static_route_configure - (optional) is a type of string
  static_route_configure = null
  # subnet - (optional) is a type of string
  subnet = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "associated_interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "country" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "show_in_address_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "static_route_configure" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fortios_firewall_object_address" "this" {
  associated_interface   = var.associated_interface
  comment                = var.comment
  country                = var.country
  end_ip                 = var.end_ip
  fqdn                   = var.fqdn
  name                   = var.name
  show_in_address_list   = var.show_in_address_list
  start_ip               = var.start_ip
  static_route_configure = var.static_route_configure
  subnet                 = var.subnet
  type                   = var.type
}
```

[top](#index)

### Outputs

```terraform
output "associated_interface" {
  description = "returns a string"
  value       = fortios_firewall_object_address.this.associated_interface
}

output "country" {
  description = "returns a string"
  value       = fortios_firewall_object_address.this.country
}

output "end_ip" {
  description = "returns a string"
  value       = fortios_firewall_object_address.this.end_ip
}

output "fqdn" {
  description = "returns a string"
  value       = fortios_firewall_object_address.this.fqdn
}

output "id" {
  description = "returns a string"
  value       = fortios_firewall_object_address.this.id
}

output "show_in_address_list" {
  description = "returns a string"
  value       = fortios_firewall_object_address.this.show_in_address_list
}

output "start_ip" {
  description = "returns a string"
  value       = fortios_firewall_object_address.this.start_ip
}

output "static_route_configure" {
  description = "returns a string"
  value       = fortios_firewall_object_address.this.static_route_configure
}

output "subnet" {
  description = "returns a string"
  value       = fortios_firewall_object_address.this.subnet
}

output "this" {
  value = fortios_firewall_object_address.this
}
```

[top](#index)