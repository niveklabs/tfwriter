# fortios_wirelesscontroller_utmprofile

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
module "fortios_wirelesscontroller_utmprofile" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_utmprofile"

  # antivirus_profile - (optional) is a type of string
  antivirus_profile = null
  # application_list - (optional) is a type of string
  application_list = null
  # comment - (optional) is a type of string
  comment = null
  # ips_sensor - (optional) is a type of string
  ips_sensor = null
  # name - (optional) is a type of string
  name = null
  # scan_botnet_connections - (optional) is a type of string
  scan_botnet_connections = null
  # utm_log - (optional) is a type of string
  utm_log = null
  # webfilter_profile - (optional) is a type of string
  webfilter_profile = null
}
```

[top](#index)

### Variables

```terraform
variable "antivirus_profile" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "application_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ips_sensor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scan_botnet_connections" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "utm_log" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webfilter_profile" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_utmprofile" "this" {
  antivirus_profile       = var.antivirus_profile
  application_list        = var.application_list
  comment                 = var.comment
  ips_sensor              = var.ips_sensor
  name                    = var.name
  scan_botnet_connections = var.scan_botnet_connections
  utm_log                 = var.utm_log
  webfilter_profile       = var.webfilter_profile
}
```

[top](#index)

### Outputs

```terraform
output "antivirus_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_utmprofile.this.antivirus_profile
}

output "application_list" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_utmprofile.this.application_list
}

output "comment" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_utmprofile.this.comment
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_utmprofile.this.id
}

output "ips_sensor" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_utmprofile.this.ips_sensor
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_utmprofile.this.name
}

output "scan_botnet_connections" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_utmprofile.this.scan_botnet_connections
}

output "utm_log" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_utmprofile.this.utm_log
}

output "webfilter_profile" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_utmprofile.this.webfilter_profile
}

output "this" {
  value = fortios_wirelesscontroller_utmprofile.this
}
```

[top](#index)