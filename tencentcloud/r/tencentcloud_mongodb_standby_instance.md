# tencentcloud_mongodb_standby_instance

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
module "tencentcloud_mongodb_standby_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_mongodb_standby_instance"

  # auto_renew_flag - (optional) is a type of number
  auto_renew_flag = null
  # available_zone - (required) is a type of string
  available_zone = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # father_instance_id - (required) is a type of string
  father_instance_id = null
  # father_instance_region - (required) is a type of string
  father_instance_region = null
  # instance_name - (required) is a type of string
  instance_name = null
  # memory - (required) is a type of number
  memory = null
  # prepaid_period - (optional) is a type of number
  prepaid_period = null
  # project_id - (optional) is a type of number
  project_id = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # volume - (required) is a type of number
  volume = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_renew_flag" {
  description = "(optional) - Auto renew flag. Valid values are `0`(NOTIFY_AND_MANUAL_RENEW), `1`(NOTIFY_AND_AUTO_RENEW) and `2`(DISABLE_NOTIFY_AND_MANUAL_RENEW). Default value is `0`. Note: only works for PREPAID instance. Only supports`0` and `1` for creation."
  type        = number
  default     = null
}

variable "available_zone" {
  description = "(required) - The available zone of the Mongodb standby instance. NOTE: must not be same with father instance's."
  type        = string
}

variable "charge_type" {
  description = "(optional) - The charge type of instance. Valid values are `PREPAID` and `POSTPAID_BY_HOUR`. Default value is `POSTPAID_BY_HOUR`. Note: TencentCloud International only supports `POSTPAID_BY_HOUR`. Caution that update operation on this field will delete old instances and create new one with new charge type."
  type        = string
  default     = null
}

variable "father_instance_id" {
  description = "(required) - Indicates the main instance ID of standby instances."
  type        = string
}

variable "father_instance_region" {
  description = "(required) - Indicates the region of main instance."
  type        = string
}

variable "instance_name" {
  description = "(required) - Name of the Mongodb instance."
  type        = string
}

variable "memory" {
  description = "(required) - Memory size. The minimum value is 2, and unit is GB. Memory and volume must be upgraded or degraded simultaneously."
  type        = number
}

variable "prepaid_period" {
  description = "(optional) - The tenancy (time unit is month) of the prepaid instance. Valid values are 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 24, 36. NOTE: it only works when charge_type is set to `PREPAID`."
  type        = number
  default     = null
}

variable "project_id" {
  description = "(optional) - ID of the project which the instance belongs."
  type        = number
  default     = null
}

variable "security_groups" {
  description = "(optional) - ID of the security group. NOTE: for instance which `engine_version` is `MONGO_40_WT`, `security_groups` is not supported."
  type        = set(string)
  default     = null
}

variable "subnet_id" {
  description = "(optional) - ID of the subnet within this VPC. The value is required if `vpc_id` is set."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The tags of the Mongodb. Key name `project` is system reserved and can't be used."
  type        = map(string)
  default     = null
}

variable "volume" {
  description = "(required) - Disk size. The minimum value is 25, and unit is GB. Memory and volume must be upgraded or degraded simultaneously."
  type        = number
}

variable "vpc_id" {
  description = "(optional) - ID of the VPC."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_mongodb_standby_instance" "this" {
  auto_renew_flag        = var.auto_renew_flag
  available_zone         = var.available_zone
  charge_type            = var.charge_type
  father_instance_id     = var.father_instance_id
  father_instance_region = var.father_instance_region
  instance_name          = var.instance_name
  memory                 = var.memory
  prepaid_period         = var.prepaid_period
  project_id             = var.project_id
  security_groups        = var.security_groups
  subnet_id              = var.subnet_id
  tags                   = var.tags
  volume                 = var.volume
  vpc_id                 = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_mongodb_standby_instance.this.create_time
}

output "engine_version" {
  description = "returns a string"
  value       = tencentcloud_mongodb_standby_instance.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_mongodb_standby_instance.this.id
}

output "machine_type" {
  description = "returns a string"
  value       = tencentcloud_mongodb_standby_instance.this.machine_type
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_mongodb_standby_instance.this.status
}

output "vip" {
  description = "returns a string"
  value       = tencentcloud_mongodb_standby_instance.this.vip
}

output "vport" {
  description = "returns a number"
  value       = tencentcloud_mongodb_standby_instance.this.vport
}

output "this" {
  value = tencentcloud_mongodb_standby_instance.this
}
```

[top](#index)