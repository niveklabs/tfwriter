# fortios_extendercontroller_extender

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
module "fortios_extendercontroller_extender" {
  source = "./modules/fortios/r/fortios_extendercontroller_extender"

  # aaa_shared_secret - (optional) is a type of string
  aaa_shared_secret = null
  # access_point_name - (optional) is a type of string
  access_point_name = null
  # admin - (required) is a type of string
  admin = null
  # at_dial_script - (optional) is a type of string
  at_dial_script = null
  # billing_start_day - (optional) is a type of number
  billing_start_day = null
  # cdma_aaa_spi - (optional) is a type of string
  cdma_aaa_spi = null
  # cdma_ha_spi - (optional) is a type of string
  cdma_ha_spi = null
  # cdma_nai - (optional) is a type of string
  cdma_nai = null
  # conn_status - (optional) is a type of number
  conn_status = null
  # description - (optional) is a type of string
  description = null
  # dial_mode - (optional) is a type of string
  dial_mode = null
  # dial_status - (optional) is a type of number
  dial_status = null
  # ext_name - (optional) is a type of string
  ext_name = null
  # fosid - (required) is a type of string
  fosid = null
  # ha_shared_secret - (optional) is a type of string
  ha_shared_secret = null
  # ifname - (optional) is a type of string
  ifname = null
  # initiated_update - (optional) is a type of string
  initiated_update = null
  # mode - (optional) is a type of string
  mode = null
  # modem_passwd - (optional) is a type of string
  modem_passwd = null
  # modem_type - (optional) is a type of string
  modem_type = null
  # multi_mode - (optional) is a type of string
  multi_mode = null
  # ppp_auth_protocol - (optional) is a type of string
  ppp_auth_protocol = null
  # ppp_echo_request - (optional) is a type of string
  ppp_echo_request = null
  # ppp_password - (optional) is a type of string
  ppp_password = null
  # ppp_username - (optional) is a type of string
  ppp_username = null
  # primary_ha - (optional) is a type of string
  primary_ha = null
  # quota_limit_mb - (optional) is a type of number
  quota_limit_mb = null
  # redial - (optional) is a type of string
  redial = null
  # redundant_intf - (optional) is a type of string
  redundant_intf = null
  # roaming - (optional) is a type of string
  roaming = null
  # role - (required) is a type of string
  role = null
  # secondary_ha - (optional) is a type of string
  secondary_ha = null
  # sim_pin - (optional) is a type of string
  sim_pin = null
  # vdom - (optional) is a type of number
  vdom = null
  # wimax_auth_protocol - (optional) is a type of string
  wimax_auth_protocol = null
  # wimax_carrier - (optional) is a type of string
  wimax_carrier = null
  # wimax_realm - (optional) is a type of string
  wimax_realm = null
}
```

[top](#index)

### Variables

```terraform
variable "aaa_shared_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "access_point_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "admin" {
  description = "(required)"
  type        = string
}

variable "at_dial_script" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "billing_start_day" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "cdma_aaa_spi" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cdma_ha_spi" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cdma_nai" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "conn_status" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dial_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dial_status" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ext_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fosid" {
  description = "(required)"
  type        = string
}

variable "ha_shared_secret" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ifname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "initiated_update" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "modem_passwd" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "modem_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "multi_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ppp_auth_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ppp_echo_request" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ppp_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ppp_username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "primary_ha" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "quota_limit_mb" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "redial" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redundant_intf" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "roaming" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "secondary_ha" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sim_pin" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vdom" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "wimax_auth_protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wimax_carrier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wimax_realm" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_extendercontroller_extender" "this" {
  # aaa_shared_secret - (optional) is a type of string
  aaa_shared_secret = var.aaa_shared_secret
  # access_point_name - (optional) is a type of string
  access_point_name = var.access_point_name
  # admin - (required) is a type of string
  admin = var.admin
  # at_dial_script - (optional) is a type of string
  at_dial_script = var.at_dial_script
  # billing_start_day - (optional) is a type of number
  billing_start_day = var.billing_start_day
  # cdma_aaa_spi - (optional) is a type of string
  cdma_aaa_spi = var.cdma_aaa_spi
  # cdma_ha_spi - (optional) is a type of string
  cdma_ha_spi = var.cdma_ha_spi
  # cdma_nai - (optional) is a type of string
  cdma_nai = var.cdma_nai
  # conn_status - (optional) is a type of number
  conn_status = var.conn_status
  # description - (optional) is a type of string
  description = var.description
  # dial_mode - (optional) is a type of string
  dial_mode = var.dial_mode
  # dial_status - (optional) is a type of number
  dial_status = var.dial_status
  # ext_name - (optional) is a type of string
  ext_name = var.ext_name
  # fosid - (required) is a type of string
  fosid = var.fosid
  # ha_shared_secret - (optional) is a type of string
  ha_shared_secret = var.ha_shared_secret
  # ifname - (optional) is a type of string
  ifname = var.ifname
  # initiated_update - (optional) is a type of string
  initiated_update = var.initiated_update
  # mode - (optional) is a type of string
  mode = var.mode
  # modem_passwd - (optional) is a type of string
  modem_passwd = var.modem_passwd
  # modem_type - (optional) is a type of string
  modem_type = var.modem_type
  # multi_mode - (optional) is a type of string
  multi_mode = var.multi_mode
  # ppp_auth_protocol - (optional) is a type of string
  ppp_auth_protocol = var.ppp_auth_protocol
  # ppp_echo_request - (optional) is a type of string
  ppp_echo_request = var.ppp_echo_request
  # ppp_password - (optional) is a type of string
  ppp_password = var.ppp_password
  # ppp_username - (optional) is a type of string
  ppp_username = var.ppp_username
  # primary_ha - (optional) is a type of string
  primary_ha = var.primary_ha
  # quota_limit_mb - (optional) is a type of number
  quota_limit_mb = var.quota_limit_mb
  # redial - (optional) is a type of string
  redial = var.redial
  # redundant_intf - (optional) is a type of string
  redundant_intf = var.redundant_intf
  # roaming - (optional) is a type of string
  roaming = var.roaming
  # role - (required) is a type of string
  role = var.role
  # secondary_ha - (optional) is a type of string
  secondary_ha = var.secondary_ha
  # sim_pin - (optional) is a type of string
  sim_pin = var.sim_pin
  # vdom - (optional) is a type of number
  vdom = var.vdom
  # wimax_auth_protocol - (optional) is a type of string
  wimax_auth_protocol = var.wimax_auth_protocol
  # wimax_carrier - (optional) is a type of string
  wimax_carrier = var.wimax_carrier
  # wimax_realm - (optional) is a type of string
  wimax_realm = var.wimax_realm
}
```

[top](#index)

### Outputs

```terraform
output "access_point_name" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.access_point_name
}

output "at_dial_script" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.at_dial_script
}

output "billing_start_day" {
  description = "returns a number"
  value       = fortios_extendercontroller_extender.this.billing_start_day
}

output "cdma_aaa_spi" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.cdma_aaa_spi
}

output "cdma_ha_spi" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.cdma_ha_spi
}

output "cdma_nai" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.cdma_nai
}

output "conn_status" {
  description = "returns a number"
  value       = fortios_extendercontroller_extender.this.conn_status
}

output "description" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.description
}

output "dial_mode" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.dial_mode
}

output "dial_status" {
  description = "returns a number"
  value       = fortios_extendercontroller_extender.this.dial_status
}

output "ext_name" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.ext_name
}

output "id" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.id
}

output "ifname" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.ifname
}

output "initiated_update" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.initiated_update
}

output "mode" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.mode
}

output "modem_type" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.modem_type
}

output "multi_mode" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.multi_mode
}

output "ppp_auth_protocol" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.ppp_auth_protocol
}

output "ppp_echo_request" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.ppp_echo_request
}

output "ppp_username" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.ppp_username
}

output "primary_ha" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.primary_ha
}

output "quota_limit_mb" {
  description = "returns a number"
  value       = fortios_extendercontroller_extender.this.quota_limit_mb
}

output "redial" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.redial
}

output "redundant_intf" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.redundant_intf
}

output "roaming" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.roaming
}

output "secondary_ha" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.secondary_ha
}

output "vdom" {
  description = "returns a number"
  value       = fortios_extendercontroller_extender.this.vdom
}

output "wimax_auth_protocol" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.wimax_auth_protocol
}

output "wimax_carrier" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.wimax_carrier
}

output "wimax_realm" {
  description = "returns a string"
  value       = fortios_extendercontroller_extender.this.wimax_realm
}

output "this" {
  value = fortios_extendercontroller_extender.this
}
```

[top](#index)