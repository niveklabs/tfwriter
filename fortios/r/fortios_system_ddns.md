# fortios_system_ddns

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
module "fortios_system_ddns" {
  source = "./modules/fortios/r/fortios_system_ddns"

  # bound_ip - (optional) is a type of string
  bound_ip = null
  # clear_text - (optional) is a type of string
  clear_text = null
  # ddns_auth - (optional) is a type of string
  ddns_auth = null
  # ddns_domain - (optional) is a type of string
  ddns_domain = null
  # ddns_key - (optional) is a type of string
  ddns_key = null
  # ddns_keyname - (optional) is a type of string
  ddns_keyname = null
  # ddns_password - (optional) is a type of string
  ddns_password = null
  # ddns_server - (required) is a type of string
  ddns_server = null
  # ddns_server_ip - (optional) is a type of string
  ddns_server_ip = null
  # ddns_sn - (optional) is a type of string
  ddns_sn = null
  # ddns_ttl - (optional) is a type of number
  ddns_ttl = null
  # ddns_username - (optional) is a type of string
  ddns_username = null
  # ddns_zone - (optional) is a type of string
  ddns_zone = null
  # ddnsid - (optional) is a type of number
  ddnsid = null
  # ssl_certificate - (optional) is a type of string
  ssl_certificate = null
  # update_interval - (optional) is a type of number
  update_interval = null
  # use_public_ip - (optional) is a type of string
  use_public_ip = null

  monitor_interface = [{
    interface_name = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bound_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "clear_text" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_auth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_keyname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_server" {
  description = "(required)"
  type        = string
}

variable "ddns_server_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_sn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ddns_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddnsid" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ssl_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "update_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "use_public_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monitor_interface" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      interface_name = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_ddns" "this" {
  bound_ip        = var.bound_ip
  clear_text      = var.clear_text
  ddns_auth       = var.ddns_auth
  ddns_domain     = var.ddns_domain
  ddns_key        = var.ddns_key
  ddns_keyname    = var.ddns_keyname
  ddns_password   = var.ddns_password
  ddns_server     = var.ddns_server
  ddns_server_ip  = var.ddns_server_ip
  ddns_sn         = var.ddns_sn
  ddns_ttl        = var.ddns_ttl
  ddns_username   = var.ddns_username
  ddns_zone       = var.ddns_zone
  ddnsid          = var.ddnsid
  ssl_certificate = var.ssl_certificate
  update_interval = var.update_interval
  use_public_ip   = var.use_public_ip

  dynamic "monitor_interface" {
    for_each = var.monitor_interface
    content {
      interface_name = monitor_interface.value["interface_name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bound_ip" {
  description = "returns a string"
  value       = fortios_system_ddns.this.bound_ip
}

output "clear_text" {
  description = "returns a string"
  value       = fortios_system_ddns.this.clear_text
}

output "ddns_auth" {
  description = "returns a string"
  value       = fortios_system_ddns.this.ddns_auth
}

output "ddns_domain" {
  description = "returns a string"
  value       = fortios_system_ddns.this.ddns_domain
}

output "ddns_key" {
  description = "returns a string"
  value       = fortios_system_ddns.this.ddns_key
  sensitive   = true
}

output "ddns_keyname" {
  description = "returns a string"
  value       = fortios_system_ddns.this.ddns_keyname
}

output "ddns_server_ip" {
  description = "returns a string"
  value       = fortios_system_ddns.this.ddns_server_ip
}

output "ddns_sn" {
  description = "returns a string"
  value       = fortios_system_ddns.this.ddns_sn
}

output "ddns_ttl" {
  description = "returns a number"
  value       = fortios_system_ddns.this.ddns_ttl
}

output "ddns_username" {
  description = "returns a string"
  value       = fortios_system_ddns.this.ddns_username
}

output "ddns_zone" {
  description = "returns a string"
  value       = fortios_system_ddns.this.ddns_zone
}

output "ddnsid" {
  description = "returns a number"
  value       = fortios_system_ddns.this.ddnsid
}

output "id" {
  description = "returns a string"
  value       = fortios_system_ddns.this.id
}

output "ssl_certificate" {
  description = "returns a string"
  value       = fortios_system_ddns.this.ssl_certificate
}

output "update_interval" {
  description = "returns a number"
  value       = fortios_system_ddns.this.update_interval
}

output "use_public_ip" {
  description = "returns a string"
  value       = fortios_system_ddns.this.use_public_ip
}

output "this" {
  value = fortios_system_ddns.this
}
```

[top](#index)