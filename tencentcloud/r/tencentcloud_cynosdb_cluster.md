# tencentcloud_cynosdb_cluster

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
module "tencentcloud_cynosdb_cluster" {
  source = "./modules/tencentcloud/r/tencentcloud_cynosdb_cluster"

  # auto_renew_flag - (optional) is a type of number
  auto_renew_flag = null
  # available_zone - (required) is a type of string
  available_zone = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # cluster_name - (required) is a type of string
  cluster_name = null
  # db_type - (required) is a type of string
  db_type = null
  # db_version - (required) is a type of string
  db_version = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # instance_cpu_core - (required) is a type of number
  instance_cpu_core = null
  # instance_maintain_duration - (optional) is a type of number
  instance_maintain_duration = null
  # instance_maintain_start_time - (optional) is a type of number
  instance_maintain_start_time = null
  # instance_maintain_weekdays - (optional) is a type of set of string
  instance_maintain_weekdays = []
  # instance_memory_size - (required) is a type of number
  instance_memory_size = null
  # password - (required) is a type of string
  password = null
  # port - (optional) is a type of number
  port = null
  # prepaid_period - (optional) is a type of number
  prepaid_period = null
  # project_id - (optional) is a type of number
  project_id = null
  # ro_group_sg - (optional) is a type of list of string
  ro_group_sg = []
  # rw_group_sg - (optional) is a type of list of string
  rw_group_sg = []
  # storage_limit - (required) is a type of number
  storage_limit = null
  # subnet_id - (required) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_renew_flag" {
  description = "(optional) - Auto renew flag. Valid values are `0`(MANUAL_RENEW), `1`(AUTO_RENEW). Default value is `0`. Only works for PREPAID cluster."
  type        = number
  default     = null
}

variable "available_zone" {
  description = "(required) - The available zone of the CynosDB Cluster."
  type        = string
}

variable "charge_type" {
  description = "(optional) - The charge type of instance. Valid values are `PREPAID` and `POSTPAID_BY_HOUR`. Default value is `POSTPAID_BY_HOUR`."
  type        = string
  default     = null
}

variable "cluster_name" {
  description = "(required) - Name of CynosDB cluster."
  type        = string
}

variable "db_type" {
  description = "(required) - Type of CynosDB, and available values include `MYSQL`."
  type        = string
}

variable "db_version" {
  description = "(required) - Version of CynosDB, which is related to `db_type`. For `MYSQL`, available value is `5.7`."
  type        = string
}

variable "force_delete" {
  description = "(optional) - Indicate whether to delete cluster instance directly or not. Default is false. If set true, the cluster and its `All RELATED INSTANCES` will be deleted instead of staying recycle bin. Note: works for both `PREPAID` and `POSTPAID_BY_HOUR` cluster."
  type        = bool
  default     = null
}

variable "instance_cpu_core" {
  description = "(required) - The number of CPU cores of read-write type instance in the CynosDB cluster. Note: modification of this field will take effect immediately, if want to upgrade on maintenance window, please upgrade from console."
  type        = number
}

variable "instance_maintain_duration" {
  description = "(optional) - Duration time for maintenance, unit in second. `3600` by default."
  type        = number
  default     = null
}

variable "instance_maintain_start_time" {
  description = "(optional) - Offset time from 00:00, unit in second. For example, 03:00am should be `10800`. `10800` by default."
  type        = number
  default     = null
}

variable "instance_maintain_weekdays" {
  description = "(optional) - Weekdays for maintenance. `[\"Mon\", \"Tue\", \"Wed\", \"Thu\", \"Fri\", \"Sat\", \"Sun\"]` by default."
  type        = set(string)
  default     = null
}

variable "instance_memory_size" {
  description = "(required) - Memory capacity of read-write type instance, unit in GB. Note: modification of this field will take effect immediately, if want to upgrade on maintenance window, please upgrade from console."
  type        = number
}

variable "password" {
  description = "(required) - Password of `root` account."
  type        = string
}

variable "port" {
  description = "(optional) - Port of CynosDB cluster."
  type        = number
  default     = null
}

variable "prepaid_period" {
  description = "(optional) - The tenancy (time unit is month) of the prepaid instance. Valid values are `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `10`, `11`, `12`, `24`, `36`. NOTE: it only works when charge_type is set to `PREPAID`."
  type        = number
  default     = null
}

variable "project_id" {
  description = "(optional) - ID of the project. `0` by default."
  type        = number
  default     = null
}

variable "ro_group_sg" {
  description = "(optional) - IDs of security group for `ro_group`."
  type        = list(string)
  default     = null
}

variable "rw_group_sg" {
  description = "(optional) - IDs of security group for `rw_group`."
  type        = list(string)
  default     = null
}

variable "storage_limit" {
  description = "(required) - Storage limit of CynosDB cluster instance, unit in GB."
  type        = number
}

variable "subnet_id" {
  description = "(required) - ID of the subnet within this VPC."
  type        = string
}

variable "tags" {
  description = "(optional) - The tags of the CynosDB cluster."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(required) - ID of the VPC."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cynosdb_cluster" "this" {
  # auto_renew_flag - (optional) is a type of number
  auto_renew_flag = var.auto_renew_flag
  # available_zone - (required) is a type of string
  available_zone = var.available_zone
  # charge_type - (optional) is a type of string
  charge_type = var.charge_type
  # cluster_name - (required) is a type of string
  cluster_name = var.cluster_name
  # db_type - (required) is a type of string
  db_type = var.db_type
  # db_version - (required) is a type of string
  db_version = var.db_version
  # force_delete - (optional) is a type of bool
  force_delete = var.force_delete
  # instance_cpu_core - (required) is a type of number
  instance_cpu_core = var.instance_cpu_core
  # instance_maintain_duration - (optional) is a type of number
  instance_maintain_duration = var.instance_maintain_duration
  # instance_maintain_start_time - (optional) is a type of number
  instance_maintain_start_time = var.instance_maintain_start_time
  # instance_maintain_weekdays - (optional) is a type of set of string
  instance_maintain_weekdays = var.instance_maintain_weekdays
  # instance_memory_size - (required) is a type of number
  instance_memory_size = var.instance_memory_size
  # password - (required) is a type of string
  password = var.password
  # port - (optional) is a type of number
  port = var.port
  # prepaid_period - (optional) is a type of number
  prepaid_period = var.prepaid_period
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # ro_group_sg - (optional) is a type of list of string
  ro_group_sg = var.ro_group_sg
  # rw_group_sg - (optional) is a type of list of string
  rw_group_sg = var.rw_group_sg
  # storage_limit - (required) is a type of number
  storage_limit = var.storage_limit
  # subnet_id - (required) is a type of string
  subnet_id = var.subnet_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_id - (required) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "charset" {
  description = "returns a string"
  value       = tencentcloud_cynosdb_cluster.this.charset
}

output "cluster_status" {
  description = "returns a string"
  value       = tencentcloud_cynosdb_cluster.this.cluster_status
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_cynosdb_cluster.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cynosdb_cluster.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = tencentcloud_cynosdb_cluster.this.instance_id
}

output "instance_maintain_weekdays" {
  description = "returns a set of string"
  value       = tencentcloud_cynosdb_cluster.this.instance_maintain_weekdays
}

output "instance_name" {
  description = "returns a string"
  value       = tencentcloud_cynosdb_cluster.this.instance_name
}

output "instance_status" {
  description = "returns a string"
  value       = tencentcloud_cynosdb_cluster.this.instance_status
}

output "instance_storage_size" {
  description = "returns a number"
  value       = tencentcloud_cynosdb_cluster.this.instance_storage_size
}

output "ro_group_addr" {
  description = "returns a list of object"
  value       = tencentcloud_cynosdb_cluster.this.ro_group_addr
}

output "ro_group_id" {
  description = "returns a string"
  value       = tencentcloud_cynosdb_cluster.this.ro_group_id
}

output "ro_group_instances" {
  description = "returns a list of object"
  value       = tencentcloud_cynosdb_cluster.this.ro_group_instances
}

output "rw_group_addr" {
  description = "returns a list of object"
  value       = tencentcloud_cynosdb_cluster.this.rw_group_addr
}

output "rw_group_id" {
  description = "returns a string"
  value       = tencentcloud_cynosdb_cluster.this.rw_group_id
}

output "rw_group_instances" {
  description = "returns a list of object"
  value       = tencentcloud_cynosdb_cluster.this.rw_group_instances
}

output "storage_used" {
  description = "returns a number"
  value       = tencentcloud_cynosdb_cluster.this.storage_used
}

output "this" {
  value = tencentcloud_cynosdb_cluster.this
}
```

[top](#index)