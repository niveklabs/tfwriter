# fortios_system_fortiguard

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
module "fortios_system_fortiguard" {
  source = "./modules/fortios/r/fortios_system_fortiguard"

  # antispam_cache - (optional) is a type of string
  antispam_cache = null
  # antispam_cache_mpercent - (optional) is a type of number
  antispam_cache_mpercent = null
  # antispam_cache_ttl - (optional) is a type of number
  antispam_cache_ttl = null
  # antispam_expiration - (optional) is a type of number
  antispam_expiration = null
  # antispam_force_off - (optional) is a type of string
  antispam_force_off = null
  # antispam_license - (optional) is a type of number
  antispam_license = null
  # antispam_timeout - (required) is a type of number
  antispam_timeout = null
  # auto_join_forticloud - (optional) is a type of string
  auto_join_forticloud = null
  # ddns_server_ip - (optional) is a type of string
  ddns_server_ip = null
  # ddns_server_port - (optional) is a type of number
  ddns_server_port = null
  # load_balance_servers - (optional) is a type of number
  load_balance_servers = null
  # outbreak_prevention_cache - (optional) is a type of string
  outbreak_prevention_cache = null
  # outbreak_prevention_cache_mpercent - (optional) is a type of number
  outbreak_prevention_cache_mpercent = null
  # outbreak_prevention_cache_ttl - (optional) is a type of number
  outbreak_prevention_cache_ttl = null
  # outbreak_prevention_expiration - (optional) is a type of number
  outbreak_prevention_expiration = null
  # outbreak_prevention_force_off - (optional) is a type of string
  outbreak_prevention_force_off = null
  # outbreak_prevention_license - (optional) is a type of number
  outbreak_prevention_license = null
  # outbreak_prevention_timeout - (required) is a type of number
  outbreak_prevention_timeout = null
  # port - (optional) is a type of string
  port = null
  # sandbox_region - (optional) is a type of string
  sandbox_region = null
  # sdns_server_ip - (optional) is a type of string
  sdns_server_ip = null
  # sdns_server_port - (optional) is a type of number
  sdns_server_port = null
  # service_account_id - (optional) is a type of string
  service_account_id = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # source_ip6 - (optional) is a type of string
  source_ip6 = null
  # update_server_location - (optional) is a type of string
  update_server_location = null
  # webfilter_cache - (optional) is a type of string
  webfilter_cache = null
  # webfilter_cache_ttl - (optional) is a type of number
  webfilter_cache_ttl = null
  # webfilter_expiration - (optional) is a type of number
  webfilter_expiration = null
  # webfilter_force_off - (optional) is a type of string
  webfilter_force_off = null
  # webfilter_license - (optional) is a type of number
  webfilter_license = null
  # webfilter_timeout - (required) is a type of number
  webfilter_timeout = null
}
```

[top](#index)

### Variables

```terraform
variable "antispam_cache" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "antispam_cache_mpercent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "antispam_cache_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "antispam_expiration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "antispam_force_off" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "antispam_license" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "antispam_timeout" {
  description = "(required)"
  type        = number
}

variable "auto_join_forticloud" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_server_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddns_server_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "load_balance_servers" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "outbreak_prevention_cache" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "outbreak_prevention_cache_mpercent" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "outbreak_prevention_cache_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "outbreak_prevention_expiration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "outbreak_prevention_force_off" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "outbreak_prevention_license" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "outbreak_prevention_timeout" {
  description = "(required)"
  type        = number
}

variable "port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sandbox_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sdns_server_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sdns_server_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "service_account_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "update_server_location" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webfilter_cache" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webfilter_cache_ttl" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "webfilter_expiration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "webfilter_force_off" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "webfilter_license" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "webfilter_timeout" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "fortios_system_fortiguard" "this" {
  antispam_cache                     = var.antispam_cache
  antispam_cache_mpercent            = var.antispam_cache_mpercent
  antispam_cache_ttl                 = var.antispam_cache_ttl
  antispam_expiration                = var.antispam_expiration
  antispam_force_off                 = var.antispam_force_off
  antispam_license                   = var.antispam_license
  antispam_timeout                   = var.antispam_timeout
  auto_join_forticloud               = var.auto_join_forticloud
  ddns_server_ip                     = var.ddns_server_ip
  ddns_server_port                   = var.ddns_server_port
  load_balance_servers               = var.load_balance_servers
  outbreak_prevention_cache          = var.outbreak_prevention_cache
  outbreak_prevention_cache_mpercent = var.outbreak_prevention_cache_mpercent
  outbreak_prevention_cache_ttl      = var.outbreak_prevention_cache_ttl
  outbreak_prevention_expiration     = var.outbreak_prevention_expiration
  outbreak_prevention_force_off      = var.outbreak_prevention_force_off
  outbreak_prevention_license        = var.outbreak_prevention_license
  outbreak_prevention_timeout        = var.outbreak_prevention_timeout
  port                               = var.port
  sandbox_region                     = var.sandbox_region
  sdns_server_ip                     = var.sdns_server_ip
  sdns_server_port                   = var.sdns_server_port
  service_account_id                 = var.service_account_id
  source_ip                          = var.source_ip
  source_ip6                         = var.source_ip6
  update_server_location             = var.update_server_location
  webfilter_cache                    = var.webfilter_cache
  webfilter_cache_ttl                = var.webfilter_cache_ttl
  webfilter_expiration               = var.webfilter_expiration
  webfilter_force_off                = var.webfilter_force_off
  webfilter_license                  = var.webfilter_license
  webfilter_timeout                  = var.webfilter_timeout
}
```

[top](#index)

### Outputs

```terraform
output "antispam_cache" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.antispam_cache
}

output "antispam_cache_mpercent" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.antispam_cache_mpercent
}

output "antispam_cache_ttl" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.antispam_cache_ttl
}

output "antispam_expiration" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.antispam_expiration
}

output "antispam_force_off" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.antispam_force_off
}

output "antispam_license" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.antispam_license
}

output "auto_join_forticloud" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.auto_join_forticloud
}

output "ddns_server_ip" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.ddns_server_ip
}

output "ddns_server_port" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.ddns_server_port
}

output "id" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.id
}

output "load_balance_servers" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.load_balance_servers
}

output "outbreak_prevention_cache" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.outbreak_prevention_cache
}

output "outbreak_prevention_cache_mpercent" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.outbreak_prevention_cache_mpercent
}

output "outbreak_prevention_cache_ttl" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.outbreak_prevention_cache_ttl
}

output "outbreak_prevention_expiration" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.outbreak_prevention_expiration
}

output "outbreak_prevention_force_off" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.outbreak_prevention_force_off
}

output "outbreak_prevention_license" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.outbreak_prevention_license
}

output "port" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.port
}

output "sandbox_region" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.sandbox_region
}

output "sdns_server_ip" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.sdns_server_ip
}

output "sdns_server_port" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.sdns_server_port
}

output "service_account_id" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.service_account_id
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.source_ip
}

output "source_ip6" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.source_ip6
}

output "update_server_location" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.update_server_location
}

output "webfilter_cache" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.webfilter_cache
}

output "webfilter_cache_ttl" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.webfilter_cache_ttl
}

output "webfilter_expiration" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.webfilter_expiration
}

output "webfilter_force_off" {
  description = "returns a string"
  value       = fortios_system_fortiguard.this.webfilter_force_off
}

output "webfilter_license" {
  description = "returns a number"
  value       = fortios_system_fortiguard.this.webfilter_license
}

output "this" {
  value = fortios_system_fortiguard.this
}
```

[top](#index)