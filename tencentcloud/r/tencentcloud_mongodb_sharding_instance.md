# tencentcloud_mongodb_sharding_instance

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
module "tencentcloud_mongodb_sharding_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_mongodb_sharding_instance"

  # auto_renew_flag - (optional) is a type of number
  auto_renew_flag = null
  # available_zone - (required) is a type of string
  available_zone = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # engine_version - (required) is a type of string
  engine_version = null
  # instance_name - (required) is a type of string
  instance_name = null
  # machine_type - (required) is a type of string
  machine_type = null
  # memory - (required) is a type of number
  memory = null
  # nodes_per_shard - (required) is a type of number
  nodes_per_shard = null
  # password - (required) is a type of string
  password = null
  # prepaid_period - (optional) is a type of number
  prepaid_period = null
  # project_id - (optional) is a type of number
  project_id = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # shard_quantity - (required) is a type of number
  shard_quantity = null
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
  description = "(required) - The available zone of the Mongodb."
  type        = string
}

variable "charge_type" {
  description = "(optional) - The charge type of instance. Valid values are `PREPAID` and `POSTPAID_BY_HOUR`. Default value is `POSTPAID_BY_HOUR`. Note: TencentCloud International only supports `POSTPAID_BY_HOUR`. Caution that update operation on this field will delete old instances and create new one with new charge type."
  type        = string
  default     = null
}

variable "engine_version" {
  description = "(required) - Version of the Mongodb, and available values include `MONGO_3_WT` (represents MongoDB 3.2 WiredTiger Edition), `MONGO_3_ROCKS` (represents MongoDB 3.2 RocksDB Edition), `MONGO_36_WT` (represents MongoDB 3.6 WiredTiger Edition) and `MONGO_40_WT` (represents MongoDB 4.0 WiredTiger Edition)."
  type        = string
}

variable "instance_name" {
  description = "(required) - Name of the Mongodb instance."
  type        = string
}

variable "machine_type" {
  description = "(required) - Type of Mongodb instance, and available values include `HIO`(or `GIO` which will be deprecated, represents high IO) and `HIO10G`(or `TGIO` which will be deprecated, represents 10-gigabit high IO)."
  type        = string
}

variable "memory" {
  description = "(required) - Memory size. The minimum value is 2, and unit is GB. Memory and volume must be upgraded or degraded simultaneously."
  type        = number
}

variable "nodes_per_shard" {
  description = "(required) - Number of nodes per shard, at least 3(one master and two slaves)."
  type        = number
}

variable "password" {
  description = "(required) - Password of this Mongodb account."
  type        = string
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

variable "shard_quantity" {
  description = "(required) - Number of sharding."
  type        = number
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
resource "tencentcloud_mongodb_sharding_instance" "this" {
  auto_renew_flag = var.auto_renew_flag
  available_zone  = var.available_zone
  charge_type     = var.charge_type
  engine_version  = var.engine_version
  instance_name   = var.instance_name
  machine_type    = var.machine_type
  memory          = var.memory
  nodes_per_shard = var.nodes_per_shard
  password        = var.password
  prepaid_period  = var.prepaid_period
  project_id      = var.project_id
  security_groups = var.security_groups
  shard_quantity  = var.shard_quantity
  subnet_id       = var.subnet_id
  tags            = var.tags
  volume          = var.volume
  vpc_id          = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_mongodb_sharding_instance.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_mongodb_sharding_instance.this.id
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_mongodb_sharding_instance.this.status
}

output "vip" {
  description = "returns a string"
  value       = tencentcloud_mongodb_sharding_instance.this.vip
}

output "vport" {
  description = "returns a number"
  value       = tencentcloud_mongodb_sharding_instance.this.vport
}

output "this" {
  value = tencentcloud_mongodb_sharding_instance.this
}
```

[top](#index)