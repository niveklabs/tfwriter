# tencentcloud_as_scaling_config

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
module "tencentcloud_as_scaling_config" {
  source = "./modules/tencentcloud/r/tencentcloud_as_scaling_config"

  # configuration_name - (required) is a type of string
  configuration_name = null
  # enhanced_monitor_service - (optional) is a type of bool
  enhanced_monitor_service = null
  # enhanced_security_service - (optional) is a type of bool
  enhanced_security_service = null
  # image_id - (required) is a type of string
  image_id = null
  # instance_tags - (optional) is a type of map of string
  instance_tags = {}
  # instance_types - (required) is a type of list of string
  instance_types = []
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
  # internet_max_bandwidth_out - (optional) is a type of number
  internet_max_bandwidth_out = null
  # keep_image_login - (optional) is a type of bool
  keep_image_login = null
  # key_ids - (optional) is a type of list of string
  key_ids = []
  # password - (optional) is a type of string
  password = null
  # project_id - (optional) is a type of number
  project_id = null
  # public_ip_assigned - (optional) is a type of bool
  public_ip_assigned = null
  # security_group_ids - (optional) is a type of list of string
  security_group_ids = []
  # system_disk_size - (optional) is a type of number
  system_disk_size = null
  # system_disk_type - (optional) is a type of string
  system_disk_type = null
  # user_data - (optional) is a type of string
  user_data = null

  data_disk = [{
    disk_size   = null
    disk_type   = null
    snapshot_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "configuration_name" {
  description = "(required) - Name of a launch configuration."
  type        = string
}

variable "enhanced_monitor_service" {
  description = "(optional) - To specify whether to enable cloud monitor service. Default is `TRUE`."
  type        = bool
  default     = null
}

variable "enhanced_security_service" {
  description = "(optional) - To specify whether to enable cloud security service. Default is `TRUE`."
  type        = bool
  default     = null
}

variable "image_id" {
  description = "(required) - An available image ID for a cvm instance."
  type        = string
}

variable "instance_tags" {
  description = "(optional) - A list of tags used to associate different resources."
  type        = map(string)
  default     = null
}

variable "instance_types" {
  description = "(required) - Specified types of CVM instances."
  type        = list(string)
}

variable "internet_charge_type" {
  description = "(optional) - Charge types for network traffic. Valid values: `BANDWIDTH_PREPAID`, `TRAFFIC_POSTPAID_BY_HOUR`, `TRAFFIC_POSTPAID_BY_HOUR` and `BANDWIDTH_PACKAGE`."
  type        = string
  default     = null
}

variable "internet_max_bandwidth_out" {
  description = "(optional) - Max bandwidth of Internet access in Mbps. Default is `0`."
  type        = number
  default     = null
}

variable "keep_image_login" {
  description = "(optional) - Specify whether to keep original settings of a CVM image. And it can't be used with password or key_ids together."
  type        = bool
  default     = null
}

variable "key_ids" {
  description = "(optional) - ID list of keys."
  type        = list(string)
  default     = null
}

variable "password" {
  description = "(optional) - Password to access."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - Specifys to which project the configuration belongs."
  type        = number
  default     = null
}

variable "public_ip_assigned" {
  description = "(optional) - Specify whether to assign an Internet IP address."
  type        = bool
  default     = null
}

variable "security_group_ids" {
  description = "(optional) - Security groups to which a CVM instance belongs."
  type        = list(string)
  default     = null
}

variable "system_disk_size" {
  description = "(optional) - Volume of system disk in GB. Default is `50`."
  type        = number
  default     = null
}

variable "system_disk_type" {
  description = "(optional) - Type of a CVM disk. Valid values: `CLOUD_PREMIUM` and `CLOUD_SSD`. Default is `CLOUD_PREMIUM`."
  type        = string
  default     = null
}

variable "user_data" {
  description = "(optional) - ase64-encoded User Data text, the length limit is 16KB."
  type        = string
  default     = null
}

variable "data_disk" {
  description = "nested block: NestingList, min items: 0, max items: 11"
  type = set(object(
    {
      disk_size   = number
      disk_type   = string
      snapshot_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_as_scaling_config" "this" {
  # configuration_name - (required) is a type of string
  configuration_name = var.configuration_name
  # enhanced_monitor_service - (optional) is a type of bool
  enhanced_monitor_service = var.enhanced_monitor_service
  # enhanced_security_service - (optional) is a type of bool
  enhanced_security_service = var.enhanced_security_service
  # image_id - (required) is a type of string
  image_id = var.image_id
  # instance_tags - (optional) is a type of map of string
  instance_tags = var.instance_tags
  # instance_types - (required) is a type of list of string
  instance_types = var.instance_types
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = var.internet_charge_type
  # internet_max_bandwidth_out - (optional) is a type of number
  internet_max_bandwidth_out = var.internet_max_bandwidth_out
  # keep_image_login - (optional) is a type of bool
  keep_image_login = var.keep_image_login
  # key_ids - (optional) is a type of list of string
  key_ids = var.key_ids
  # password - (optional) is a type of string
  password = var.password
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # public_ip_assigned - (optional) is a type of bool
  public_ip_assigned = var.public_ip_assigned
  # security_group_ids - (optional) is a type of list of string
  security_group_ids = var.security_group_ids
  # system_disk_size - (optional) is a type of number
  system_disk_size = var.system_disk_size
  # system_disk_type - (optional) is a type of string
  system_disk_type = var.system_disk_type
  # user_data - (optional) is a type of string
  user_data = var.user_data

  dynamic "data_disk" {
    for_each = var.data_disk
    content {
      # disk_size - (optional) is a type of number
      disk_size = data_disk.value["disk_size"]
      # disk_type - (optional) is a type of string
      disk_type = data_disk.value["disk_type"]
      # snapshot_id - (optional) is a type of string
      snapshot_id = data_disk.value["snapshot_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_as_scaling_config.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_as_scaling_config.this.id
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_as_scaling_config.this.status
}

output "this" {
  value = tencentcloud_as_scaling_config.this
}
```

[top](#index)