# panos_general_settings

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_general_settings" {
  source = "./modules/panos/r/panos_general_settings"

  # dns_primary - (optional) is a type of string
  dns_primary = null
  # dns_secondary - (optional) is a type of string
  dns_secondary = null
  # domain - (optional) is a type of string
  domain = null
  # hostname - (optional) is a type of string
  hostname = null
  # ntp_primary_address - (optional) is a type of string
  ntp_primary_address = null
  # ntp_primary_algorithm - (optional) is a type of string
  ntp_primary_algorithm = null
  # ntp_primary_auth_key - (optional) is a type of string
  ntp_primary_auth_key = null
  # ntp_primary_auth_type - (optional) is a type of string
  ntp_primary_auth_type = null
  # ntp_primary_key_id - (optional) is a type of number
  ntp_primary_key_id = null
  # ntp_secondary_address - (optional) is a type of string
  ntp_secondary_address = null
  # ntp_secondary_algorithm - (optional) is a type of string
  ntp_secondary_algorithm = null
  # ntp_secondary_auth_key - (optional) is a type of string
  ntp_secondary_auth_key = null
  # ntp_secondary_auth_type - (optional) is a type of string
  ntp_secondary_auth_type = null
  # ntp_secondary_key_id - (optional) is a type of number
  ntp_secondary_key_id = null
  # proxy_password - (optional) is a type of string
  proxy_password = null
  # proxy_port - (optional) is a type of number
  proxy_port = null
  # proxy_server - (optional) is a type of string
  proxy_server = null
  # proxy_user - (optional) is a type of string
  proxy_user = null
  # timezone - (optional) is a type of string
  timezone = null
  # update_server - (optional) is a type of string
  update_server = null
  # verify_update_server - (optional) is a type of bool
  verify_update_server = null
}
```

[top](#index)

### Variables

```terraform
variable "dns_primary" {
  description = "(optional) - Primary DNS IP address"
  type        = string
  default     = null
}

variable "dns_secondary" {
  description = "(optional) - Secondary DNS IP address"
  type        = string
  default     = null
}

variable "domain" {
  description = "(optional) - Domain"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional) - The firewall hostname"
  type        = string
  default     = null
}

variable "ntp_primary_address" {
  description = "(optional) - Primary NTP server"
  type        = string
  default     = null
}

variable "ntp_primary_algorithm" {
  description = "(optional) - NTP symmetric-key algorithm (sha1 or md5)"
  type        = string
  default     = null
}

variable "ntp_primary_auth_key" {
  description = "(optional) - NTP symmetric-key auth key"
  type        = string
  default     = null
}

variable "ntp_primary_auth_type" {
  description = "(optional) - NTP auth type (none, autokey, symmetric-key)"
  type        = string
  default     = null
}

variable "ntp_primary_key_id" {
  description = "(optional) - NTP symmetric-key key ID"
  type        = number
  default     = null
}

variable "ntp_secondary_address" {
  description = "(optional) - Secondary NTP server"
  type        = string
  default     = null
}

variable "ntp_secondary_algorithm" {
  description = "(optional) - NTP symmetric-key algorithm (sha1 or md5)"
  type        = string
  default     = null
}

variable "ntp_secondary_auth_key" {
  description = "(optional) - NTP symmetric-key auth key"
  type        = string
  default     = null
}

variable "ntp_secondary_auth_type" {
  description = "(optional) - NTP auth type (none, autokey, symmetric-key)"
  type        = string
  default     = null
}

variable "ntp_secondary_key_id" {
  description = "(optional) - NTP symmetric-key key ID"
  type        = number
  default     = null
}

variable "proxy_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "proxy_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_user" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timezone" {
  description = "(optional) - Timezone"
  type        = string
  default     = null
}

variable "update_server" {
  description = "(optional) - PANOS update server"
  type        = string
  default     = null
}

variable "verify_update_server" {
  description = "(optional) - Verify update server identity"
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "panos_general_settings" "this" {
  dns_primary             = var.dns_primary
  dns_secondary           = var.dns_secondary
  domain                  = var.domain
  hostname                = var.hostname
  ntp_primary_address     = var.ntp_primary_address
  ntp_primary_algorithm   = var.ntp_primary_algorithm
  ntp_primary_auth_key    = var.ntp_primary_auth_key
  ntp_primary_auth_type   = var.ntp_primary_auth_type
  ntp_primary_key_id      = var.ntp_primary_key_id
  ntp_secondary_address   = var.ntp_secondary_address
  ntp_secondary_algorithm = var.ntp_secondary_algorithm
  ntp_secondary_auth_key  = var.ntp_secondary_auth_key
  ntp_secondary_auth_type = var.ntp_secondary_auth_type
  ntp_secondary_key_id    = var.ntp_secondary_key_id
  proxy_password          = var.proxy_password
  proxy_port              = var.proxy_port
  proxy_server            = var.proxy_server
  proxy_user              = var.proxy_user
  timezone                = var.timezone
  update_server           = var.update_server
  verify_update_server    = var.verify_update_server
}
```

[top](#index)

### Outputs

```terraform
output "dns_primary" {
  description = "returns a string"
  value       = panos_general_settings.this.dns_primary
}

output "dns_secondary" {
  description = "returns a string"
  value       = panos_general_settings.this.dns_secondary
}

output "domain" {
  description = "returns a string"
  value       = panos_general_settings.this.domain
}

output "hostname" {
  description = "returns a string"
  value       = panos_general_settings.this.hostname
}

output "id" {
  description = "returns a string"
  value       = panos_general_settings.this.id
}

output "ntp_primary_address" {
  description = "returns a string"
  value       = panos_general_settings.this.ntp_primary_address
}

output "ntp_primary_algorithm" {
  description = "returns a string"
  value       = panos_general_settings.this.ntp_primary_algorithm
}

output "ntp_primary_auth_key" {
  description = "returns a string"
  value       = panos_general_settings.this.ntp_primary_auth_key
}

output "ntp_primary_auth_type" {
  description = "returns a string"
  value       = panos_general_settings.this.ntp_primary_auth_type
}

output "ntp_primary_key_id" {
  description = "returns a number"
  value       = panos_general_settings.this.ntp_primary_key_id
}

output "ntp_secondary_address" {
  description = "returns a string"
  value       = panos_general_settings.this.ntp_secondary_address
}

output "ntp_secondary_algorithm" {
  description = "returns a string"
  value       = panos_general_settings.this.ntp_secondary_algorithm
}

output "ntp_secondary_auth_key" {
  description = "returns a string"
  value       = panos_general_settings.this.ntp_secondary_auth_key
}

output "ntp_secondary_auth_type" {
  description = "returns a string"
  value       = panos_general_settings.this.ntp_secondary_auth_type
}

output "ntp_secondary_key_id" {
  description = "returns a number"
  value       = panos_general_settings.this.ntp_secondary_key_id
}

output "proxy_password" {
  description = "returns a string"
  value       = panos_general_settings.this.proxy_password
  sensitive   = true
}

output "proxy_password_enc" {
  description = "returns a string"
  value       = panos_general_settings.this.proxy_password_enc
  sensitive   = true
}

output "proxy_port" {
  description = "returns a number"
  value       = panos_general_settings.this.proxy_port
}

output "proxy_server" {
  description = "returns a string"
  value       = panos_general_settings.this.proxy_server
}

output "proxy_user" {
  description = "returns a string"
  value       = panos_general_settings.this.proxy_user
}

output "timezone" {
  description = "returns a string"
  value       = panos_general_settings.this.timezone
}

output "this" {
  value = panos_general_settings.this
}
```

[top](#index)