# tencentcloud_cbs_storage

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_cbs_storage" {
  source = "./modules/tencentcloud/r/tencentcloud_cbs_storage"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # encrypt - (optional) is a type of bool
  encrypt = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # period - (optional) is a type of number
  period = null
  # prepaid_period - (optional) is a type of number
  prepaid_period = null
  # prepaid_renew_flag - (optional) is a type of string
  prepaid_renew_flag = null
  # project_id - (optional) is a type of number
  project_id = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # storage_name - (required) is a type of string
  storage_name = null
  # storage_size - (required) is a type of number
  storage_size = null
  # storage_type - (required) is a type of string
  storage_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # throughput_performance - (optional) is a type of number
  throughput_performance = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required) - The available zone that the CBS instance locates at."
  type        = string
}

variable "charge_type" {
  description = "(optional) - The charge type of CBS instance. Valid values are `PREPAID` and `POSTPAID_BY_HOUR`. The default is `POSTPAID_BY_HOUR`."
  type        = string
  default     = null
}

variable "encrypt" {
  description = "(optional) - Indicates whether CBS is encrypted."
  type        = bool
  default     = null
}

variable "force_delete" {
  description = "(optional) - Indicate whether to delete CBS instance directly or not. Default is false. If set true, the instance will be deleted instead of staying recycle bin."
  type        = bool
  default     = null
}

variable "period" {
  description = "(optional) - The purchased usage period of CBS. Valid values: [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 24, 36]."
  type        = number
  default     = null
}

variable "prepaid_period" {
  description = "(optional) - The tenancy (time unit is month) of the prepaid instance, NOTE: it only works when charge_type is set to `PREPAID`. Valid values are 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 24, 36."
  type        = number
  default     = null
}

variable "prepaid_renew_flag" {
  description = "(optional) - Auto Renewal flag. Value range: `NOTIFY_AND_AUTO_RENEW`: Notify expiry and renew automatically, `NOTIFY_AND_MANUAL_RENEW`: Notify expiry but do not renew automatically, `DISABLE_NOTIFY_AND_MANUAL_RENEW`: Neither notify expiry nor renew automatically. Default value range: `NOTIFY_AND_MANUAL_RENEW`: Notify expiry but do not renew automatically. NOTE: it only works when charge_type is set to `PREPAID`."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - ID of the project to which the instance belongs."
  type        = number
  default     = null
}

variable "snapshot_id" {
  description = "(optional) - ID of the snapshot. If specified, created the CBS by this snapshot."
  type        = string
  default     = null
}

variable "storage_name" {
  description = "(required) - Name of CBS. The maximum length can not exceed 60 bytes."
  type        = string
}

variable "storage_size" {
  description = "(required) - Volume of CBS, and unit is GB. If storage type is `CLOUD_SSD`, the size range is [100, 16000], and the others are [10-16000]."
  type        = number
}

variable "storage_type" {
  description = "(required) - Type of CBS medium. Valid values: CLOUD_BASIC, CLOUD_PREMIUM, CLOUD_SSD, CLOUD_TSSD and CLOUD_HSSD."
  type        = string
}

variable "tags" {
  description = "(optional) - The available tags within this CBS."
  type        = map(string)
  default     = null
}

variable "throughput_performance" {
  description = "(optional) - Add extra performance to the data disk. Only works when disk type is `CLOUD_TSSD` or `CLOUD_HSSD`."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cbs_storage" "this" {
  # availability_zone - (required) is a type of string
  availability_zone = var.availability_zone
  # charge_type - (optional) is a type of string
  charge_type = var.charge_type
  # encrypt - (optional) is a type of bool
  encrypt = var.encrypt
  # force_delete - (optional) is a type of bool
  force_delete = var.force_delete
  # period - (optional) is a type of number
  period = var.period
  # prepaid_period - (optional) is a type of number
  prepaid_period = var.prepaid_period
  # prepaid_renew_flag - (optional) is a type of string
  prepaid_renew_flag = var.prepaid_renew_flag
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # snapshot_id - (optional) is a type of string
  snapshot_id = var.snapshot_id
  # storage_name - (required) is a type of string
  storage_name = var.storage_name
  # storage_size - (required) is a type of number
  storage_size = var.storage_size
  # storage_type - (required) is a type of string
  storage_type = var.storage_type
  # tags - (optional) is a type of map of string
  tags = var.tags
  # throughput_performance - (optional) is a type of number
  throughput_performance = var.throughput_performance
}
```

[top](#index)

### Outputs

```terraform
output "attached" {
  description = "returns a bool"
  value       = tencentcloud_cbs_storage.this.attached
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cbs_storage.this.id
}

output "prepaid_period" {
  description = "returns a number"
  value       = tencentcloud_cbs_storage.this.prepaid_period
}

output "prepaid_renew_flag" {
  description = "returns a string"
  value       = tencentcloud_cbs_storage.this.prepaid_renew_flag
}

output "snapshot_id" {
  description = "returns a string"
  value       = tencentcloud_cbs_storage.this.snapshot_id
}

output "storage_status" {
  description = "returns a string"
  value       = tencentcloud_cbs_storage.this.storage_status
}

output "this" {
  value = tencentcloud_cbs_storage.this
}
```

[top](#index)