# tencentcloud_mysql_instance

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
module "tencentcloud_mysql_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_mysql_instance"

  # auto_renew_flag - (optional) is a type of number
  auto_renew_flag = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # first_slave_zone - (optional) is a type of string
  first_slave_zone = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # instance_name - (required) is a type of string
  instance_name = null
  # internet_service - (optional) is a type of number
  internet_service = null
  # intranet_port - (optional) is a type of number
  intranet_port = null
  # mem_size - (required) is a type of number
  mem_size = null
  # parameters - (optional) is a type of map of string
  parameters = {}
  # pay_type - (optional) is a type of number
  pay_type = null
  # period - (optional) is a type of number
  period = null
  # prepaid_period - (optional) is a type of number
  prepaid_period = null
  # project_id - (optional) is a type of number
  project_id = null
  # root_password - (required) is a type of string
  root_password = null
  # second_slave_zone - (optional) is a type of string
  second_slave_zone = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # slave_deploy_mode - (optional) is a type of number
  slave_deploy_mode = null
  # slave_sync_mode - (optional) is a type of number
  slave_sync_mode = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # volume_size - (required) is a type of number
  volume_size = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_renew_flag" {
  description = "(optional) - Auto renew flag. NOTES: Only supported prepaid instance."
  type        = number
  default     = null
}

variable "availability_zone" {
  description = "(optional) - Indicates which availability zone will be used."
  type        = string
  default     = null
}

variable "charge_type" {
  description = "(optional) - Pay type of instance. Valid values:`PREPAID`, `POSTPAID`. Default is `POSTPAID`."
  type        = string
  default     = null
}

variable "engine_version" {
  description = "(optional) - The version number of the database engine to use. Supported versions include 5.5/5.6/5.7/8.0, and default is 5.7."
  type        = string
  default     = null
}

variable "first_slave_zone" {
  description = "(optional) - Zone information about first slave instance."
  type        = string
  default     = null
}

variable "force_delete" {
  description = "(optional) - Indicate whether to delete instance directly or not. Default is `false`. If set true, the instance will be deleted instead of staying recycle bin. Note: only works for `PREPAID` instance. When the main mysql instance set true, this para of the readonly mysql instance will not take effect."
  type        = bool
  default     = null
}

variable "instance_name" {
  description = "(required) - The name of a mysql instance."
  type        = string
}

variable "internet_service" {
  description = "(optional) - Indicates whether to enable the access to an instance from public network: 0 - No, 1 - Yes."
  type        = number
  default     = null
}

variable "intranet_port" {
  description = "(optional) - Public access port. Valid value ranges: [1024~65535]. The default value is `3306`."
  type        = number
  default     = null
}

variable "mem_size" {
  description = "(required) - Memory size (in MB)."
  type        = number
}

variable "parameters" {
  description = "(optional) - List of parameters to use."
  type        = map(string)
  default     = null
}

variable "pay_type" {
  description = "(optional) - Pay type of instance. Valid values: `0`, `1`. `0`: prepaid, `1`: postpaid."
  type        = number
  default     = null
}

variable "period" {
  description = "(optional) - Period of instance. NOTES: Only supported prepaid instance."
  type        = number
  default     = null
}

variable "prepaid_period" {
  description = "(optional) - Period of instance. NOTES: Only supported prepaid instance."
  type        = number
  default     = null
}

variable "project_id" {
  description = "(optional) - Project ID, default value is 0."
  type        = number
  default     = null
}

variable "root_password" {
  description = "(required) - Password of root account. This parameter can be specified when you purchase master instances, but it should be ignored when you purchase read-only instances or disaster recovery instances."
  type        = string
}

variable "second_slave_zone" {
  description = "(optional) - Zone information about second slave instance."
  type        = string
  default     = null
}

variable "security_groups" {
  description = "(optional) - Security groups to use."
  type        = set(string)
  default     = null
}

variable "slave_deploy_mode" {
  description = "(optional) - Availability zone deployment method. Available values: 0 - Single availability zone; 1 - Multiple availability zones."
  type        = number
  default     = null
}

variable "slave_sync_mode" {
  description = "(optional) - Data replication mode. 0 - Async replication; 1 - Semisync replication; 2 - Strongsync replication."
  type        = number
  default     = null
}

variable "subnet_id" {
  description = "(optional) - Private network ID. If `vpc_id` is set, this value is required."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Instance tags."
  type        = map(string)
  default     = null
}

variable "volume_size" {
  description = "(required) - Disk size (in GB)."
  type        = number
}

variable "vpc_id" {
  description = "(optional) - ID of VPC, which can be modified once every 24 hours and can't be removed."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_mysql_instance" "this" {
  # auto_renew_flag - (optional) is a type of number
  auto_renew_flag = var.auto_renew_flag
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # charge_type - (optional) is a type of string
  charge_type = var.charge_type
  # engine_version - (optional) is a type of string
  engine_version = var.engine_version
  # first_slave_zone - (optional) is a type of string
  first_slave_zone = var.first_slave_zone
  # force_delete - (optional) is a type of bool
  force_delete = var.force_delete
  # instance_name - (required) is a type of string
  instance_name = var.instance_name
  # internet_service - (optional) is a type of number
  internet_service = var.internet_service
  # intranet_port - (optional) is a type of number
  intranet_port = var.intranet_port
  # mem_size - (required) is a type of number
  mem_size = var.mem_size
  # parameters - (optional) is a type of map of string
  parameters = var.parameters
  # pay_type - (optional) is a type of number
  pay_type = var.pay_type
  # period - (optional) is a type of number
  period = var.period
  # prepaid_period - (optional) is a type of number
  prepaid_period = var.prepaid_period
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # root_password - (required) is a type of string
  root_password = var.root_password
  # second_slave_zone - (optional) is a type of string
  second_slave_zone = var.second_slave_zone
  # security_groups - (optional) is a type of set of string
  security_groups = var.security_groups
  # slave_deploy_mode - (optional) is a type of number
  slave_deploy_mode = var.slave_deploy_mode
  # slave_sync_mode - (optional) is a type of number
  slave_sync_mode = var.slave_sync_mode
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # volume_size - (required) is a type of number
  volume_size = var.volume_size
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_zone" {
  description = "returns a string"
  value       = tencentcloud_mysql_instance.this.availability_zone
}

output "gtid" {
  description = "returns a number"
  value       = tencentcloud_mysql_instance.this.gtid
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_mysql_instance.this.id
}

output "internet_host" {
  description = "returns a string"
  value       = tencentcloud_mysql_instance.this.internet_host
}

output "internet_port" {
  description = "returns a number"
  value       = tencentcloud_mysql_instance.this.internet_port
}

output "intranet_ip" {
  description = "returns a string"
  value       = tencentcloud_mysql_instance.this.intranet_ip
}

output "locked" {
  description = "returns a number"
  value       = tencentcloud_mysql_instance.this.locked
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_mysql_instance.this.status
}

output "task_status" {
  description = "returns a number"
  value       = tencentcloud_mysql_instance.this.task_status
}

output "this" {
  value = tencentcloud_mysql_instance.this
}
```

[top](#index)