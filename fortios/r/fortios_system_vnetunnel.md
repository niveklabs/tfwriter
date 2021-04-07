# fortios_system_vnetunnel

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
module "fortios_system_vnetunnel" {
  source = "./modules/fortios/r/fortios_system_vnetunnel"

  # bmr_hostname - (optional) is a type of string
  bmr_hostname = null
  # br - (optional) is a type of string
  br = null
  # interface - (optional) is a type of string
  interface = null
  # ipv4_address - (optional) is a type of string
  ipv4_address = null
  # mode - (optional) is a type of string
  mode = null
  # ssl_certificate - (optional) is a type of string
  ssl_certificate = null
  # status - (optional) is a type of string
  status = null
  # update_url - (optional) is a type of string
  update_url = null
}
```

[top](#index)

### Variables

```terraform
variable "bmr_hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "br" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "update_url" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_vnetunnel" "this" {
  # bmr_hostname - (optional) is a type of string
  bmr_hostname = var.bmr_hostname
  # br - (optional) is a type of string
  br = var.br
  # interface - (optional) is a type of string
  interface = var.interface
  # ipv4_address - (optional) is a type of string
  ipv4_address = var.ipv4_address
  # mode - (optional) is a type of string
  mode = var.mode
  # ssl_certificate - (optional) is a type of string
  ssl_certificate = var.ssl_certificate
  # status - (optional) is a type of string
  status = var.status
  # update_url - (optional) is a type of string
  update_url = var.update_url
}
```

[top](#index)

### Outputs

```terraform
output "br" {
  description = "returns a string"
  value       = fortios_system_vnetunnel.this.br
}

output "id" {
  description = "returns a string"
  value       = fortios_system_vnetunnel.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_system_vnetunnel.this.interface
}

output "ipv4_address" {
  description = "returns a string"
  value       = fortios_system_vnetunnel.this.ipv4_address
}

output "mode" {
  description = "returns a string"
  value       = fortios_system_vnetunnel.this.mode
}

output "ssl_certificate" {
  description = "returns a string"
  value       = fortios_system_vnetunnel.this.ssl_certificate
}

output "status" {
  description = "returns a string"
  value       = fortios_system_vnetunnel.this.status
}

output "update_url" {
  description = "returns a string"
  value       = fortios_system_vnetunnel.this.update_url
}

output "this" {
  value = fortios_system_vnetunnel.this
}
```

[top](#index)