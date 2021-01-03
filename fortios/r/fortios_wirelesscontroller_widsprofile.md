# fortios_wirelesscontroller_widsprofile

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
module "fortios_wirelesscontroller_widsprofile" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_widsprofile"

  # ap_auto_suppress - (optional) is a type of string
  ap_auto_suppress = null
  # ap_bgscan_disable_day - (optional) is a type of string
  ap_bgscan_disable_day = null
  # ap_bgscan_disable_end - (optional) is a type of string
  ap_bgscan_disable_end = null
  # ap_bgscan_disable_start - (optional) is a type of string
  ap_bgscan_disable_start = null
  # ap_bgscan_duration - (optional) is a type of number
  ap_bgscan_duration = null
  # ap_bgscan_idle - (optional) is a type of number
  ap_bgscan_idle = null
  # ap_bgscan_intv - (optional) is a type of number
  ap_bgscan_intv = null
  # ap_bgscan_period - (optional) is a type of number
  ap_bgscan_period = null
  # ap_bgscan_report_intv - (optional) is a type of number
  ap_bgscan_report_intv = null
  # ap_fgscan_report_intv - (optional) is a type of number
  ap_fgscan_report_intv = null
  # ap_scan - (optional) is a type of string
  ap_scan = null
  # ap_scan_passive - (optional) is a type of string
  ap_scan_passive = null
  # asleap_attack - (optional) is a type of string
  asleap_attack = null
  # assoc_flood_thresh - (optional) is a type of number
  assoc_flood_thresh = null
  # assoc_flood_time - (optional) is a type of number
  assoc_flood_time = null
  # assoc_frame_flood - (optional) is a type of string
  assoc_frame_flood = null
  # auth_flood_thresh - (optional) is a type of number
  auth_flood_thresh = null
  # auth_flood_time - (optional) is a type of number
  auth_flood_time = null
  # auth_frame_flood - (optional) is a type of string
  auth_frame_flood = null
  # comment - (optional) is a type of string
  comment = null
  # deauth_broadcast - (optional) is a type of string
  deauth_broadcast = null
  # deauth_unknown_src_thresh - (optional) is a type of number
  deauth_unknown_src_thresh = null
  # eapol_fail_flood - (optional) is a type of string
  eapol_fail_flood = null
  # eapol_fail_intv - (optional) is a type of number
  eapol_fail_intv = null
  # eapol_fail_thresh - (optional) is a type of number
  eapol_fail_thresh = null
  # eapol_logoff_flood - (optional) is a type of string
  eapol_logoff_flood = null
  # eapol_logoff_intv - (optional) is a type of number
  eapol_logoff_intv = null
  # eapol_logoff_thresh - (optional) is a type of number
  eapol_logoff_thresh = null
  # eapol_pre_fail_flood - (optional) is a type of string
  eapol_pre_fail_flood = null
  # eapol_pre_fail_intv - (optional) is a type of number
  eapol_pre_fail_intv = null
  # eapol_pre_fail_thresh - (optional) is a type of number
  eapol_pre_fail_thresh = null
  # eapol_pre_succ_flood - (optional) is a type of string
  eapol_pre_succ_flood = null
  # eapol_pre_succ_intv - (optional) is a type of number
  eapol_pre_succ_intv = null
  # eapol_pre_succ_thresh - (optional) is a type of number
  eapol_pre_succ_thresh = null
  # eapol_start_flood - (optional) is a type of string
  eapol_start_flood = null
  # eapol_start_intv - (optional) is a type of number
  eapol_start_intv = null
  # eapol_start_thresh - (optional) is a type of number
  eapol_start_thresh = null
  # eapol_succ_flood - (optional) is a type of string
  eapol_succ_flood = null
  # eapol_succ_intv - (optional) is a type of number
  eapol_succ_intv = null
  # eapol_succ_thresh - (optional) is a type of number
  eapol_succ_thresh = null
  # invalid_mac_oui - (optional) is a type of string
  invalid_mac_oui = null
  # long_duration_attack - (optional) is a type of string
  long_duration_attack = null
  # long_duration_thresh - (optional) is a type of number
  long_duration_thresh = null
  # name - (optional) is a type of string
  name = null
  # null_ssid_probe_resp - (optional) is a type of string
  null_ssid_probe_resp = null
  # sensor_mode - (optional) is a type of string
  sensor_mode = null
  # spoofed_deauth - (optional) is a type of string
  spoofed_deauth = null
  # weak_wep_iv - (optional) is a type of string
  weak_wep_iv = null
  # wireless_bridge - (optional) is a type of string
  wireless_bridge = null
}
```

[top](#index)

### Variables

```terraform
variable "ap_auto_suppress" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ap_bgscan_disable_day" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ap_bgscan_disable_end" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ap_bgscan_disable_start" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ap_bgscan_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ap_bgscan_idle" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ap_bgscan_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ap_bgscan_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ap_bgscan_report_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ap_fgscan_report_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ap_scan" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ap_scan_passive" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "asleap_attack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "assoc_flood_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "assoc_flood_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "assoc_frame_flood" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_flood_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_flood_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auth_frame_flood" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deauth_broadcast" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deauth_unknown_src_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_fail_flood" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eapol_fail_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_fail_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_logoff_flood" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eapol_logoff_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_logoff_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_pre_fail_flood" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eapol_pre_fail_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_pre_fail_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_pre_succ_flood" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eapol_pre_succ_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_pre_succ_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_start_flood" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eapol_start_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_start_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_succ_flood" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eapol_succ_intv" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "eapol_succ_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "invalid_mac_oui" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "long_duration_attack" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "long_duration_thresh" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "null_ssid_probe_resp" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "sensor_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spoofed_deauth" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "weak_wep_iv" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wireless_bridge" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_widsprofile" "this" {
  ap_auto_suppress          = var.ap_auto_suppress
  ap_bgscan_disable_day     = var.ap_bgscan_disable_day
  ap_bgscan_disable_end     = var.ap_bgscan_disable_end
  ap_bgscan_disable_start   = var.ap_bgscan_disable_start
  ap_bgscan_duration        = var.ap_bgscan_duration
  ap_bgscan_idle            = var.ap_bgscan_idle
  ap_bgscan_intv            = var.ap_bgscan_intv
  ap_bgscan_period          = var.ap_bgscan_period
  ap_bgscan_report_intv     = var.ap_bgscan_report_intv
  ap_fgscan_report_intv     = var.ap_fgscan_report_intv
  ap_scan                   = var.ap_scan
  ap_scan_passive           = var.ap_scan_passive
  asleap_attack             = var.asleap_attack
  assoc_flood_thresh        = var.assoc_flood_thresh
  assoc_flood_time          = var.assoc_flood_time
  assoc_frame_flood         = var.assoc_frame_flood
  auth_flood_thresh         = var.auth_flood_thresh
  auth_flood_time           = var.auth_flood_time
  auth_frame_flood          = var.auth_frame_flood
  comment                   = var.comment
  deauth_broadcast          = var.deauth_broadcast
  deauth_unknown_src_thresh = var.deauth_unknown_src_thresh
  eapol_fail_flood          = var.eapol_fail_flood
  eapol_fail_intv           = var.eapol_fail_intv
  eapol_fail_thresh         = var.eapol_fail_thresh
  eapol_logoff_flood        = var.eapol_logoff_flood
  eapol_logoff_intv         = var.eapol_logoff_intv
  eapol_logoff_thresh       = var.eapol_logoff_thresh
  eapol_pre_fail_flood      = var.eapol_pre_fail_flood
  eapol_pre_fail_intv       = var.eapol_pre_fail_intv
  eapol_pre_fail_thresh     = var.eapol_pre_fail_thresh
  eapol_pre_succ_flood      = var.eapol_pre_succ_flood
  eapol_pre_succ_intv       = var.eapol_pre_succ_intv
  eapol_pre_succ_thresh     = var.eapol_pre_succ_thresh
  eapol_start_flood         = var.eapol_start_flood
  eapol_start_intv          = var.eapol_start_intv
  eapol_start_thresh        = var.eapol_start_thresh
  eapol_succ_flood          = var.eapol_succ_flood
  eapol_succ_intv           = var.eapol_succ_intv
  eapol_succ_thresh         = var.eapol_succ_thresh
  invalid_mac_oui           = var.invalid_mac_oui
  long_duration_attack      = var.long_duration_attack
  long_duration_thresh      = var.long_duration_thresh
  name                      = var.name
  null_ssid_probe_resp      = var.null_ssid_probe_resp
  sensor_mode               = var.sensor_mode
  spoofed_deauth            = var.spoofed_deauth
  weak_wep_iv               = var.weak_wep_iv
  wireless_bridge           = var.wireless_bridge
}
```

[top](#index)

### Outputs

```terraform
output "ap_auto_suppress" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_auto_suppress
}

output "ap_bgscan_disable_day" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_bgscan_disable_day
}

output "ap_bgscan_disable_end" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_bgscan_disable_end
}

output "ap_bgscan_disable_start" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_bgscan_disable_start
}

output "ap_bgscan_duration" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_bgscan_duration
}

output "ap_bgscan_idle" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_bgscan_idle
}

output "ap_bgscan_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_bgscan_intv
}

output "ap_bgscan_period" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_bgscan_period
}

output "ap_bgscan_report_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_bgscan_report_intv
}

output "ap_fgscan_report_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_fgscan_report_intv
}

output "ap_scan" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_scan
}

output "ap_scan_passive" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.ap_scan_passive
}

output "asleap_attack" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.asleap_attack
}

output "assoc_flood_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.assoc_flood_thresh
}

output "assoc_flood_time" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.assoc_flood_time
}

output "assoc_frame_flood" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.assoc_frame_flood
}

output "auth_flood_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.auth_flood_thresh
}

output "auth_flood_time" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.auth_flood_time
}

output "auth_frame_flood" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.auth_frame_flood
}

output "comment" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.comment
}

output "deauth_broadcast" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.deauth_broadcast
}

output "deauth_unknown_src_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.deauth_unknown_src_thresh
}

output "eapol_fail_flood" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_fail_flood
}

output "eapol_fail_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_fail_intv
}

output "eapol_fail_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_fail_thresh
}

output "eapol_logoff_flood" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_logoff_flood
}

output "eapol_logoff_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_logoff_intv
}

output "eapol_logoff_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_logoff_thresh
}

output "eapol_pre_fail_flood" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_pre_fail_flood
}

output "eapol_pre_fail_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_pre_fail_intv
}

output "eapol_pre_fail_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_pre_fail_thresh
}

output "eapol_pre_succ_flood" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_pre_succ_flood
}

output "eapol_pre_succ_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_pre_succ_intv
}

output "eapol_pre_succ_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_pre_succ_thresh
}

output "eapol_start_flood" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_start_flood
}

output "eapol_start_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_start_intv
}

output "eapol_start_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_start_thresh
}

output "eapol_succ_flood" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_succ_flood
}

output "eapol_succ_intv" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_succ_intv
}

output "eapol_succ_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.eapol_succ_thresh
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.id
}

output "invalid_mac_oui" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.invalid_mac_oui
}

output "long_duration_attack" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.long_duration_attack
}

output "long_duration_thresh" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_widsprofile.this.long_duration_thresh
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.name
}

output "null_ssid_probe_resp" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.null_ssid_probe_resp
}

output "sensor_mode" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.sensor_mode
}

output "spoofed_deauth" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.spoofed_deauth
}

output "weak_wep_iv" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.weak_wep_iv
}

output "wireless_bridge" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_widsprofile.this.wireless_bridge
}

output "this" {
  value = fortios_wirelesscontroller_widsprofile.this
}
```

[top](#index)