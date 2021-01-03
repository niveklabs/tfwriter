# fortios_alertemail_setting

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
module "fortios_alertemail_setting" {
  source = "./modules/fortios/r/fortios_alertemail_setting"

  # admin_login_logs - (optional) is a type of string
  admin_login_logs = null
  # alert_interval - (optional) is a type of number
  alert_interval = null
  # amc_interface_bypass_mode - (optional) is a type of string
  amc_interface_bypass_mode = null
  # antivirus_logs - (optional) is a type of string
  antivirus_logs = null
  # configuration_changes_logs - (optional) is a type of string
  configuration_changes_logs = null
  # critical_interval - (optional) is a type of number
  critical_interval = null
  # debug_interval - (optional) is a type of number
  debug_interval = null
  # email_interval - (optional) is a type of number
  email_interval = null
  # emergency_interval - (optional) is a type of number
  emergency_interval = null
  # error_interval - (optional) is a type of number
  error_interval = null
  # fds_license_expiring_days - (optional) is a type of number
  fds_license_expiring_days = null
  # fds_license_expiring_warning - (optional) is a type of string
  fds_license_expiring_warning = null
  # fds_update_logs - (optional) is a type of string
  fds_update_logs = null
  # filter_mode - (optional) is a type of string
  filter_mode = null
  # fips_cc_errors - (optional) is a type of string
  fips_cc_errors = null
  # firewall_authentication_failure_logs - (optional) is a type of string
  firewall_authentication_failure_logs = null
  # fortiguard_log_quota_warning - (optional) is a type of string
  fortiguard_log_quota_warning = null
  # fsso_disconnect_logs - (optional) is a type of string
  fsso_disconnect_logs = null
  # ha_logs - (optional) is a type of string
  ha_logs = null
  # information_interval - (optional) is a type of number
  information_interval = null
  # ips_logs - (optional) is a type of string
  ips_logs = null
  # ipsec_errors_logs - (optional) is a type of string
  ipsec_errors_logs = null
  # local_disk_usage - (optional) is a type of number
  local_disk_usage = null
  # log_disk_usage_warning - (optional) is a type of string
  log_disk_usage_warning = null
  # mailto1 - (optional) is a type of string
  mailto1 = null
  # mailto2 - (optional) is a type of string
  mailto2 = null
  # mailto3 - (optional) is a type of string
  mailto3 = null
  # notification_interval - (optional) is a type of number
  notification_interval = null
  # ppp_errors_logs - (optional) is a type of string
  ppp_errors_logs = null
  # severity - (optional) is a type of string
  severity = null
  # ssh_logs - (optional) is a type of string
  ssh_logs = null
  # sslvpn_authentication_errors_logs - (optional) is a type of string
  sslvpn_authentication_errors_logs = null
  # username - (optional) is a type of string
  username = null
  # violation_traffic_logs - (optional) is a type of string
  violation_traffic_logs = null
  # warning_interval - (optional) is a type of number
  warning_interval = null
  # webfilter_logs - (optional) is a type of string
  webfilter_logs = null
}
```

[top](#index)

### Variables

```terraform
variable "admin_login_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alert_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "amc_interface_bypass_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "antivirus_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "configuration_changes_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "critical_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "debug_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "email_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "emergency_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "error_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fds_license_expiring_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fds_license_expiring_warning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fds_update_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fips_cc_errors" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "firewall_authentication_failure_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fortiguard_log_quota_warning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "fsso_disconnect_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ha_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "information_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ips_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipsec_errors_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "local_disk_usage" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "log_disk_usage_warning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mailto1" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mailto2" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "mailto3" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notification_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ppp_errors_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "severity" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sslvpn_authentication_errors_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "violation_traffic_logs" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "warning_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "webfilter_logs" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_alertemail_setting" "this" {
  admin_login_logs                     = var.admin_login_logs
  alert_interval                       = var.alert_interval
  amc_interface_bypass_mode            = var.amc_interface_bypass_mode
  antivirus_logs                       = var.antivirus_logs
  configuration_changes_logs           = var.configuration_changes_logs
  critical_interval                    = var.critical_interval
  debug_interval                       = var.debug_interval
  email_interval                       = var.email_interval
  emergency_interval                   = var.emergency_interval
  error_interval                       = var.error_interval
  fds_license_expiring_days            = var.fds_license_expiring_days
  fds_license_expiring_warning         = var.fds_license_expiring_warning
  fds_update_logs                      = var.fds_update_logs
  filter_mode                          = var.filter_mode
  fips_cc_errors                       = var.fips_cc_errors
  firewall_authentication_failure_logs = var.firewall_authentication_failure_logs
  fortiguard_log_quota_warning         = var.fortiguard_log_quota_warning
  fsso_disconnect_logs                 = var.fsso_disconnect_logs
  ha_logs                              = var.ha_logs
  information_interval                 = var.information_interval
  ips_logs                             = var.ips_logs
  ipsec_errors_logs                    = var.ipsec_errors_logs
  local_disk_usage                     = var.local_disk_usage
  log_disk_usage_warning               = var.log_disk_usage_warning
  mailto1                              = var.mailto1
  mailto2                              = var.mailto2
  mailto3                              = var.mailto3
  notification_interval                = var.notification_interval
  ppp_errors_logs                      = var.ppp_errors_logs
  severity                             = var.severity
  ssh_logs                             = var.ssh_logs
  sslvpn_authentication_errors_logs    = var.sslvpn_authentication_errors_logs
  username                             = var.username
  violation_traffic_logs               = var.violation_traffic_logs
  warning_interval                     = var.warning_interval
  webfilter_logs                       = var.webfilter_logs
}
```

[top](#index)

### Outputs

```terraform
output "admin_login_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.admin_login_logs
}

output "alert_interval" {
  description = "returns a number"
  value       = fortios_alertemail_setting.this.alert_interval
}

output "amc_interface_bypass_mode" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.amc_interface_bypass_mode
}

output "antivirus_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.antivirus_logs
}

output "configuration_changes_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.configuration_changes_logs
}

output "critical_interval" {
  description = "returns a number"
  value       = fortios_alertemail_setting.this.critical_interval
}

output "debug_interval" {
  description = "returns a number"
  value       = fortios_alertemail_setting.this.debug_interval
}

output "email_interval" {
  description = "returns a number"
  value       = fortios_alertemail_setting.this.email_interval
}

output "emergency_interval" {
  description = "returns a number"
  value       = fortios_alertemail_setting.this.emergency_interval
}

output "error_interval" {
  description = "returns a number"
  value       = fortios_alertemail_setting.this.error_interval
}

output "fds_license_expiring_days" {
  description = "returns a number"
  value       = fortios_alertemail_setting.this.fds_license_expiring_days
}

output "fds_license_expiring_warning" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.fds_license_expiring_warning
}

output "fds_update_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.fds_update_logs
}

output "filter_mode" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.filter_mode
}

output "fips_cc_errors" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.fips_cc_errors
}

output "firewall_authentication_failure_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.firewall_authentication_failure_logs
}

output "fortiguard_log_quota_warning" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.fortiguard_log_quota_warning
}

output "fsso_disconnect_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.fsso_disconnect_logs
}

output "ha_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.ha_logs
}

output "id" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.id
}

output "information_interval" {
  description = "returns a number"
  value       = fortios_alertemail_setting.this.information_interval
}

output "ips_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.ips_logs
}

output "ipsec_errors_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.ipsec_errors_logs
}

output "local_disk_usage" {
  description = "returns a number"
  value       = fortios_alertemail_setting.this.local_disk_usage
}

output "log_disk_usage_warning" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.log_disk_usage_warning
}

output "mailto1" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.mailto1
}

output "mailto2" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.mailto2
}

output "mailto3" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.mailto3
}

output "notification_interval" {
  description = "returns a number"
  value       = fortios_alertemail_setting.this.notification_interval
}

output "ppp_errors_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.ppp_errors_logs
}

output "severity" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.severity
}

output "ssh_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.ssh_logs
}

output "sslvpn_authentication_errors_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.sslvpn_authentication_errors_logs
}

output "username" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.username
}

output "violation_traffic_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.violation_traffic_logs
}

output "warning_interval" {
  description = "returns a number"
  value       = fortios_alertemail_setting.this.warning_interval
}

output "webfilter_logs" {
  description = "returns a string"
  value       = fortios_alertemail_setting.this.webfilter_logs
}

output "this" {
  value = fortios_alertemail_setting.this
}
```

[top](#index)