# fortios_endpointcontrol_fctems

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
module "fortios_endpointcontrol_fctems" {
  source = "./modules/fortios/r/fortios_endpointcontrol_fctems"

  # admin_password - (optional) is a type of string
  admin_password = null
  # admin_username - (optional) is a type of string
  admin_username = null
  # call_timeout - (optional) is a type of number
  call_timeout = null
  # certificate - (optional) is a type of string
  certificate = null
  # cloud_server_type - (optional) is a type of string
  cloud_server_type = null
  # fortinetone_cloud_authentication - (optional) is a type of string
  fortinetone_cloud_authentication = null
  # https_port - (optional) is a type of number
  https_port = null
  # name - (optional) is a type of string
  name = null
  # pull_avatars - (optional) is a type of string
  pull_avatars = null
  # pull_sysinfo - (optional) is a type of string
  pull_sysinfo = null
  # pull_tags - (optional) is a type of string
  pull_tags = null
  # pull_vulnerabilities - (optional) is a type of string
  pull_vulnerabilities = null
  # serial_number - (optional) is a type of string
  serial_number = null
  # server - (optional) is a type of string
  server = null
  # source_ip - (optional) is a type of string
  source_ip = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "call_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloud_server_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortinetone_cloud_authentication" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "https_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pull_avatars" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pull_sysinfo" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pull_tags" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pull_vulnerabilities" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "serial_number" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_endpointcontrol_fctems" "this" {
  admin_password                   = var.admin_password
  admin_username                   = var.admin_username
  call_timeout                     = var.call_timeout
  certificate                      = var.certificate
  cloud_server_type                = var.cloud_server_type
  fortinetone_cloud_authentication = var.fortinetone_cloud_authentication
  https_port                       = var.https_port
  name                             = var.name
  pull_avatars                     = var.pull_avatars
  pull_sysinfo                     = var.pull_sysinfo
  pull_tags                        = var.pull_tags
  pull_vulnerabilities             = var.pull_vulnerabilities
  serial_number                    = var.serial_number
  server                           = var.server
  source_ip                        = var.source_ip
}
```

[top](#index)

### Outputs

```terraform
output "admin_username" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.admin_username
}

output "call_timeout" {
  description = "returns a number"
  value       = fortios_endpointcontrol_fctems.this.call_timeout
}

output "certificate" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.certificate
}

output "cloud_server_type" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.cloud_server_type
}

output "fortinetone_cloud_authentication" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.fortinetone_cloud_authentication
}

output "https_port" {
  description = "returns a number"
  value       = fortios_endpointcontrol_fctems.this.https_port
}

output "id" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.id
}

output "name" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.name
}

output "pull_avatars" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.pull_avatars
}

output "pull_sysinfo" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.pull_sysinfo
}

output "pull_tags" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.pull_tags
}

output "pull_vulnerabilities" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.pull_vulnerabilities
}

output "serial_number" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.serial_number
}

output "server" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.server
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_endpointcontrol_fctems.this.source_ip
}

output "this" {
  value = fortios_endpointcontrol_fctems.this
}
```

[top](#index)