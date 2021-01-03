# fortios_logdisk_setting

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
module "fortios_logdisk_setting" {
  source = "./modules/fortios/r/fortios_logdisk_setting"

  # diskfull - (optional) is a type of string
  diskfull = null
  # dlp_archive_quota - (optional) is a type of number
  dlp_archive_quota = null
  # full_final_warning_threshold - (optional) is a type of number
  full_final_warning_threshold = null
  # full_first_warning_threshold - (optional) is a type of number
  full_first_warning_threshold = null
  # full_second_warning_threshold - (optional) is a type of number
  full_second_warning_threshold = null
  # ips_archive - (optional) is a type of string
  ips_archive = null
  # log_quota - (optional) is a type of number
  log_quota = null
  # max_log_file_size - (optional) is a type of number
  max_log_file_size = null
  # max_policy_packet_capture_size - (optional) is a type of number
  max_policy_packet_capture_size = null
  # maximum_log_age - (optional) is a type of number
  maximum_log_age = null
  # report_quota - (optional) is a type of number
  report_quota = null
  # roll_day - (optional) is a type of string
  roll_day = null
  # roll_schedule - (optional) is a type of string
  roll_schedule = null
  # roll_time - (optional) is a type of string
  roll_time = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # status - (required) is a type of string
  status = null
  # upload - (optional) is a type of string
  upload = null
  # upload_delete_files - (optional) is a type of string
  upload_delete_files = null
  # upload_destination - (optional) is a type of string
  upload_destination = null
  # upload_ssl_conn - (optional) is a type of string
  upload_ssl_conn = null
  # uploaddir - (optional) is a type of string
  uploaddir = null
  # uploadip - (optional) is a type of string
  uploadip = null
  # uploadpass - (optional) is a type of string
  uploadpass = null
  # uploadport - (optional) is a type of number
  uploadport = null
  # uploadsched - (optional) is a type of string
  uploadsched = null
  # uploadtime - (optional) is a type of string
  uploadtime = null
  # uploadtype - (optional) is a type of string
  uploadtype = null
  # uploaduser - (optional) is a type of string
  uploaduser = null
}
```

[top](#index)

### Variables

```terraform
variable "diskfull" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dlp_archive_quota" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "full_final_warning_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "full_first_warning_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "full_second_warning_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ips_archive" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "log_quota" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_log_file_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "max_policy_packet_capture_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_log_age" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "report_quota" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "roll_day" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "roll_schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "roll_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(required)"
  type        = string
}

variable "upload" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_delete_files" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_destination" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "upload_ssl_conn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uploaddir" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uploadip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uploadpass" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uploadport" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "uploadsched" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uploadtime" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uploadtype" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uploaduser" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_logdisk_setting" "this" {
  diskfull                       = var.diskfull
  dlp_archive_quota              = var.dlp_archive_quota
  full_final_warning_threshold   = var.full_final_warning_threshold
  full_first_warning_threshold   = var.full_first_warning_threshold
  full_second_warning_threshold  = var.full_second_warning_threshold
  ips_archive                    = var.ips_archive
  log_quota                      = var.log_quota
  max_log_file_size              = var.max_log_file_size
  max_policy_packet_capture_size = var.max_policy_packet_capture_size
  maximum_log_age                = var.maximum_log_age
  report_quota                   = var.report_quota
  roll_day                       = var.roll_day
  roll_schedule                  = var.roll_schedule
  roll_time                      = var.roll_time
  source_ip                      = var.source_ip
  status                         = var.status
  upload                         = var.upload
  upload_delete_files            = var.upload_delete_files
  upload_destination             = var.upload_destination
  upload_ssl_conn                = var.upload_ssl_conn
  uploaddir                      = var.uploaddir
  uploadip                       = var.uploadip
  uploadpass                     = var.uploadpass
  uploadport                     = var.uploadport
  uploadsched                    = var.uploadsched
  uploadtime                     = var.uploadtime
  uploadtype                     = var.uploadtype
  uploaduser                     = var.uploaduser
}
```

[top](#index)

### Outputs

```terraform
output "diskfull" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.diskfull
}

output "dlp_archive_quota" {
  description = "returns a number"
  value       = fortios_logdisk_setting.this.dlp_archive_quota
}

output "full_final_warning_threshold" {
  description = "returns a number"
  value       = fortios_logdisk_setting.this.full_final_warning_threshold
}

output "full_first_warning_threshold" {
  description = "returns a number"
  value       = fortios_logdisk_setting.this.full_first_warning_threshold
}

output "full_second_warning_threshold" {
  description = "returns a number"
  value       = fortios_logdisk_setting.this.full_second_warning_threshold
}

output "id" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.id
}

output "ips_archive" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.ips_archive
}

output "log_quota" {
  description = "returns a number"
  value       = fortios_logdisk_setting.this.log_quota
}

output "max_log_file_size" {
  description = "returns a number"
  value       = fortios_logdisk_setting.this.max_log_file_size
}

output "max_policy_packet_capture_size" {
  description = "returns a number"
  value       = fortios_logdisk_setting.this.max_policy_packet_capture_size
}

output "maximum_log_age" {
  description = "returns a number"
  value       = fortios_logdisk_setting.this.maximum_log_age
}

output "report_quota" {
  description = "returns a number"
  value       = fortios_logdisk_setting.this.report_quota
}

output "roll_day" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.roll_day
}

output "roll_schedule" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.roll_schedule
}

output "roll_time" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.roll_time
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.source_ip
}

output "upload" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.upload
}

output "upload_delete_files" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.upload_delete_files
}

output "upload_destination" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.upload_destination
}

output "upload_ssl_conn" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.upload_ssl_conn
}

output "uploaddir" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.uploaddir
}

output "uploadip" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.uploadip
}

output "uploadport" {
  description = "returns a number"
  value       = fortios_logdisk_setting.this.uploadport
}

output "uploadsched" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.uploadsched
}

output "uploadtime" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.uploadtime
}

output "uploadtype" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.uploadtype
}

output "uploaduser" {
  description = "returns a string"
  value       = fortios_logdisk_setting.this.uploaduser
}

output "this" {
  value = fortios_logdisk_setting.this
}
```

[top](#index)