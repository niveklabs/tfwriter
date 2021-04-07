# tencentcloud_instance

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
module "tencentcloud_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_instance"

  # allocate_public_ip - (optional) is a type of bool
  allocate_public_ip = null
  # availability_zone - (required) is a type of string
  availability_zone = null
  # cam_role_name - (optional) is a type of string
  cam_role_name = null
  # cdh_host_id - (optional) is a type of string
  cdh_host_id = null
  # cdh_instance_type - (optional) is a type of string
  cdh_instance_type = null
  # disable_monitor_service - (optional) is a type of bool
  disable_monitor_service = null
  # disable_security_service - (optional) is a type of bool
  disable_security_service = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # hostname - (optional) is a type of string
  hostname = null
  # image_id - (required) is a type of string
  image_id = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # instance_charge_type_prepaid_period - (optional) is a type of number
  instance_charge_type_prepaid_period = null
  # instance_charge_type_prepaid_renew_flag - (optional) is a type of string
  instance_charge_type_prepaid_renew_flag = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
  # internet_max_bandwidth_out - (optional) is a type of number
  internet_max_bandwidth_out = null
  # keep_image_login - (optional) is a type of bool
  keep_image_login = null
  # key_name - (optional) is a type of string
  key_name = null
  # password - (optional) is a type of string
  password = null
  # placement_group_id - (optional) is a type of string
  placement_group_id = null
  # private_ip - (optional) is a type of string
  private_ip = null
  # project_id - (optional) is a type of number
  project_id = null
  # running_flag - (optional) is a type of bool
  running_flag = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # spot_instance_type - (optional) is a type of string
  spot_instance_type = null
  # spot_max_price - (optional) is a type of string
  spot_max_price = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # system_disk_id - (optional) is a type of string
  system_disk_id = null
  # system_disk_size - (optional) is a type of number
  system_disk_size = null
  # system_disk_type - (optional) is a type of string
  system_disk_type = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user_data - (optional) is a type of string
  user_data = null
  # user_data_raw - (optional) is a type of string
  user_data_raw = null
  # vpc_id - (optional) is a type of string
  vpc_id = null

  data_disks = [{
    data_disk_id           = null
    data_disk_size         = null
    data_disk_snapshot_id  = null
    data_disk_type         = null
    delete_with_instance   = null
    encrypt                = null
    throughput_performance = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allocate_public_ip" {
  description = "(optional) - Associate a public IP address with an instance in a VPC or Classic. Boolean value, Default is false."
  type        = bool
  default     = null
}

variable "availability_zone" {
  description = "(required) - The available zone for the CVM instance."
  type        = string
}

variable "cam_role_name" {
  description = "(optional) - CAM role name authorized to access."
  type        = string
  default     = null
}

variable "cdh_host_id" {
  description = "(optional) - Id of cdh instance. Note: it only works when instance_charge_type is set to `CDHPAID`."
  type        = string
  default     = null
}

variable "cdh_instance_type" {
  description = "(optional) - Type of instance created on cdh, the value of this parameter is in the format of CDH_XCXG based on the number of CPU cores and memory capacity. Note: it only works when instance_charge_type is set to `CDHPAID`."
  type        = string
  default     = null
}

variable "disable_monitor_service" {
  description = "(optional) - Disable enhance service for monitor, it is enabled by default. When this options is set, monitor agent won't be installed."
  type        = bool
  default     = null
}

variable "disable_security_service" {
  description = "(optional) - Disable enhance service for security, it is enabled by default. When this options is set, security agent won't be installed."
  type        = bool
  default     = null
}

variable "force_delete" {
  description = "(optional) - Indicate whether to force delete the instance. Default is `false`. If set true, the instance will be permanently deleted instead of being moved into the recycle bin. Note: only works for `PREPAID` instance."
  type        = bool
  default     = null
}

variable "hostname" {
  description = "(optional) - The hostname of the instance. Windows instance: The name should be a combination of 2 to 15 characters comprised of letters (case insensitive), numbers, and hyphens (-). Period (.) is not supported, and the name cannot be a string of pure numbers. Other types (such as Linux) of instances: The name should be a combination of 2 to 60 characters, supporting multiple periods (.). The piece between two periods is composed of letters (case insensitive), numbers, and hyphens (-)."
  type        = string
  default     = null
}

variable "image_id" {
  description = "(required) - The image to use for the instance. Changing `image_id` will cause the instance to be destroyed and re-created."
  type        = string
}

variable "instance_charge_type" {
  description = "(optional) - The charge type of instance. Valid values are `PREPAID`, `POSTPAID_BY_HOUR`, `SPOTPAID` and `CDHPAID`. The default is `POSTPAID_BY_HOUR`. Note: TencentCloud International only supports `POSTPAID_BY_HOUR` and `CDHPAID`. `PREPAID` instance may not allow to delete before expired. `SPOTPAID` instance must set `spot_instance_type` and `spot_max_price` at the same time. `CDHPAID` instance must set `cdh_instance_type` and `cdh_host_id`."
  type        = string
  default     = null
}

variable "instance_charge_type_prepaid_period" {
  description = "(optional) - The tenancy (time unit is month) of the prepaid instance, NOTE: it only works when instance_charge_type is set to `PREPAID`. Valid values are `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `10`, `11`, `12`, `24`, `36`."
  type        = number
  default     = null
}

variable "instance_charge_type_prepaid_renew_flag" {
  description = "(optional) - Auto renewal flag. Valid values: `NOTIFY_AND_AUTO_RENEW`: notify upon expiration and renew automatically, `NOTIFY_AND_MANUAL_RENEW`: notify upon expiration but do not renew automatically, `DISABLE_NOTIFY_AND_MANUAL_RENEW`: neither notify upon expiration nor renew automatically. Default value: `NOTIFY_AND_MANUAL_RENEW`. If this parameter is specified as `NOTIFY_AND_AUTO_RENEW`, the instance will be automatically renewed on a monthly basis if the account balance is sufficient. NOTE: it only works when instance_charge_type is set to `PREPAID`."
  type        = string
  default     = null
}

variable "instance_name" {
  description = "(optional) - The name of the instance. The max length of instance_name is 60, and default value is `Terraform-CVM-Instance`."
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional) - The type of the instance."
  type        = string
  default     = null
}

variable "internet_charge_type" {
  description = "(optional) - Internet charge type of the instance, Valid values are `BANDWIDTH_PREPAID`, `TRAFFIC_POSTPAID_BY_HOUR`, `BANDWIDTH_POSTPAID_BY_HOUR` and `BANDWIDTH_PACKAGE`. This value does not need to be set when `allocate_public_ip` is false."
  type        = string
  default     = null
}

variable "internet_max_bandwidth_out" {
  description = "(optional) - Maximum outgoing bandwidth to the public network, measured in Mbps (Mega bits per second). This value does not need to be set when `allocate_public_ip` is false."
  type        = number
  default     = null
}

variable "keep_image_login" {
  description = "(optional) - Whether to keep image login or not, default is `false`. When the image type is private or shared or imported, this parameter can be set `true`."
  type        = bool
  default     = null
}

variable "key_name" {
  description = "(optional) - The key pair to use for the instance, it looks like `skey-16jig7tx`."
  type        = string
  default     = null
}

variable "password" {
  description = "(optional) - Password for the instance. In order for the new password to take effect, the instance will be restarted after the password change."
  type        = string
  default     = null
}

variable "placement_group_id" {
  description = "(optional) - The ID of a placement group."
  type        = string
  default     = null
}

variable "private_ip" {
  description = "(optional) - The private IP to be assigned to this instance, must be in the provided subnet and available."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project the instance belongs to, default to 0."
  type        = number
  default     = null
}

variable "running_flag" {
  description = "(optional) - Set instance to running or stop. Default value is true, the instance will shutdown when this flag is false."
  type        = bool
  default     = null
}

variable "security_groups" {
  description = "(optional) - A list of security group IDs to associate with."
  type        = set(string)
  default     = null
}

variable "spot_instance_type" {
  description = "(optional) - Type of spot instance, only support `ONE-TIME` now. Note: it only works when instance_charge_type is set to `SPOTPAID`."
  type        = string
  default     = null
}

variable "spot_max_price" {
  description = "(optional) - Max price of a spot instance, is the format of decimal string, for example \"0.50\". Note: it only works when instance_charge_type is set to `SPOTPAID`."
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional) - The ID of a VPC subnet. If you want to create instances in a VPC network, this parameter must be set."
  type        = string
  default     = null
}

variable "system_disk_id" {
  description = "(optional) - System disk snapshot ID used to initialize the system disk. When system disk type is `LOCAL_BASIC` and `LOCAL_SSD`, disk id is not supported."
  type        = string
  default     = null
}

variable "system_disk_size" {
  description = "(optional) - Size of the system disk. Valid value ranges: (50~1000). and unit is GB. Default is 50GB."
  type        = number
  default     = null
}

variable "system_disk_type" {
  description = "(optional) - System disk type. For more information on limits of system disk types, see [Storage Overview](https://intl.cloud.tencent.com/document/product/213/4952). Valid values: `LOCAL_BASIC`: local disk, `LOCAL_SSD`: local SSD disk, `CLOUD_BASIC`: HDD cloud disk, `CLOUD_SSD`: SSD, `CLOUD_PREMIUM`: Premium Cloud Storage. NOTE: `LOCAL_BASIC` and `LOCAL_SSD` are deprecated."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - A mapping of tags to assign to the resource. For tag limits, please refer to [Use Limits](https://intl.cloud.tencent.com/document/product/651/13354)."
  type        = map(string)
  default     = null
}

variable "user_data" {
  description = "(optional) - The user data to be injected into this instance. Must be base64 encoded and up to 16 KB."
  type        = string
  default     = null
}

variable "user_data_raw" {
  description = "(optional) - The user data to be injected into this instance, in plain text. Conflicts with `user_data`. Up to 16 KB after base64 encoded."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - The ID of a VPC network. If you want to create instances in a VPC network, this parameter must be set."
  type        = string
  default     = null
}

variable "data_disks" {
  description = "nested block: NestingList, min items: 0, max items: 10"
  type = set(object(
    {
      data_disk_id           = string
      data_disk_size         = number
      data_disk_snapshot_id  = string
      data_disk_type         = string
      delete_with_instance   = bool
      encrypt                = bool
      throughput_performance = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_instance" "this" {
  # allocate_public_ip - (optional) is a type of bool
  allocate_public_ip = var.allocate_public_ip
  # availability_zone - (required) is a type of string
  availability_zone = var.availability_zone
  # cam_role_name - (optional) is a type of string
  cam_role_name = var.cam_role_name
  # cdh_host_id - (optional) is a type of string
  cdh_host_id = var.cdh_host_id
  # cdh_instance_type - (optional) is a type of string
  cdh_instance_type = var.cdh_instance_type
  # disable_monitor_service - (optional) is a type of bool
  disable_monitor_service = var.disable_monitor_service
  # disable_security_service - (optional) is a type of bool
  disable_security_service = var.disable_security_service
  # force_delete - (optional) is a type of bool
  force_delete = var.force_delete
  # hostname - (optional) is a type of string
  hostname = var.hostname
  # image_id - (required) is a type of string
  image_id = var.image_id
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = var.instance_charge_type
  # instance_charge_type_prepaid_period - (optional) is a type of number
  instance_charge_type_prepaid_period = var.instance_charge_type_prepaid_period
  # instance_charge_type_prepaid_renew_flag - (optional) is a type of string
  instance_charge_type_prepaid_renew_flag = var.instance_charge_type_prepaid_renew_flag
  # instance_name - (optional) is a type of string
  instance_name = var.instance_name
  # instance_type - (optional) is a type of string
  instance_type = var.instance_type
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = var.internet_charge_type
  # internet_max_bandwidth_out - (optional) is a type of number
  internet_max_bandwidth_out = var.internet_max_bandwidth_out
  # keep_image_login - (optional) is a type of bool
  keep_image_login = var.keep_image_login
  # key_name - (optional) is a type of string
  key_name = var.key_name
  # password - (optional) is a type of string
  password = var.password
  # placement_group_id - (optional) is a type of string
  placement_group_id = var.placement_group_id
  # private_ip - (optional) is a type of string
  private_ip = var.private_ip
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # running_flag - (optional) is a type of bool
  running_flag = var.running_flag
  # security_groups - (optional) is a type of set of string
  security_groups = var.security_groups
  # spot_instance_type - (optional) is a type of string
  spot_instance_type = var.spot_instance_type
  # spot_max_price - (optional) is a type of string
  spot_max_price = var.spot_max_price
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
  # system_disk_id - (optional) is a type of string
  system_disk_id = var.system_disk_id
  # system_disk_size - (optional) is a type of number
  system_disk_size = var.system_disk_size
  # system_disk_type - (optional) is a type of string
  system_disk_type = var.system_disk_type
  # tags - (optional) is a type of map of string
  tags = var.tags
  # user_data - (optional) is a type of string
  user_data = var.user_data
  # user_data_raw - (optional) is a type of string
  user_data_raw = var.user_data_raw
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id

  dynamic "data_disks" {
    for_each = var.data_disks
    content {
      # data_disk_id - (optional) is a type of string
      data_disk_id = data_disks.value["data_disk_id"]
      # data_disk_size - (required) is a type of number
      data_disk_size = data_disks.value["data_disk_size"]
      # data_disk_snapshot_id - (optional) is a type of string
      data_disk_snapshot_id = data_disks.value["data_disk_snapshot_id"]
      # data_disk_type - (required) is a type of string
      data_disk_type = data_disks.value["data_disk_type"]
      # delete_with_instance - (optional) is a type of bool
      delete_with_instance = data_disks.value["delete_with_instance"]
      # encrypt - (optional) is a type of bool
      encrypt = data_disks.value["encrypt"]
      # throughput_performance - (optional) is a type of number
      throughput_performance = data_disks.value["throughput_performance"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_instance.this.create_time
}

output "expired_time" {
  description = "returns a string"
  value       = tencentcloud_instance.this.expired_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_instance.this.id
}

output "instance_charge_type_prepaid_renew_flag" {
  description = "returns a string"
  value       = tencentcloud_instance.this.instance_charge_type_prepaid_renew_flag
}

output "instance_status" {
  description = "returns a string"
  value       = tencentcloud_instance.this.instance_status
}

output "instance_type" {
  description = "returns a string"
  value       = tencentcloud_instance.this.instance_type
}

output "internet_charge_type" {
  description = "returns a string"
  value       = tencentcloud_instance.this.internet_charge_type
}

output "internet_max_bandwidth_out" {
  description = "returns a number"
  value       = tencentcloud_instance.this.internet_max_bandwidth_out
}

output "key_name" {
  description = "returns a string"
  value       = tencentcloud_instance.this.key_name
}

output "private_ip" {
  description = "returns a string"
  value       = tencentcloud_instance.this.private_ip
}

output "public_ip" {
  description = "returns a string"
  value       = tencentcloud_instance.this.public_ip
}

output "security_groups" {
  description = "returns a set of string"
  value       = tencentcloud_instance.this.security_groups
}

output "subnet_id" {
  description = "returns a string"
  value       = tencentcloud_instance.this.subnet_id
}

output "system_disk_id" {
  description = "returns a string"
  value       = tencentcloud_instance.this.system_disk_id
}

output "vpc_id" {
  description = "returns a string"
  value       = tencentcloud_instance.this.vpc_id
}

output "this" {
  value = tencentcloud_instance.this
}
```

[top](#index)