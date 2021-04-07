# tencentcloud_redis_instance

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
module "tencentcloud_redis_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_redis_instance"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # mem_size - (required) is a type of number
  mem_size = null
  # name - (optional) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # port - (optional) is a type of number
  port = null
  # prepaid_period - (optional) is a type of number
  prepaid_period = null
  # project_id - (optional) is a type of number
  project_id = null
  # redis_replicas_num - (optional) is a type of number
  redis_replicas_num = null
  # redis_shard_num - (optional) is a type of number
  redis_shard_num = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (optional) is a type of string
  type = null
  # type_id - (optional) is a type of number
  type_id = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required) - The available zone ID of an instance to be created, please refer to `tencentcloud_redis_zone_config.list`."
  type        = string
}

variable "charge_type" {
  description = "(optional) - The charge type of instance. Valid values: `PREPAID` and `POSTPAID`. Default value is `POSTPAID`. Note: TencentCloud International only supports `POSTPAID`. Caution that update operation on this field will delete old instances and create new with new charge type."
  type        = string
  default     = null
}

variable "force_delete" {
  description = "(optional) - Indicate whether to delete Redis instance directly or not. Default is false. If set true, the instance will be deleted instead of staying recycle bin. Note: only works for `PREPAID` instance."
  type        = bool
  default     = null
}

variable "mem_size" {
  description = "(required) - The memory volume of an available instance(in MB), please refer to `tencentcloud_redis_zone_config.list[zone].mem_sizes`. When redis is standard type, it represents total memory size of the instance; when Redis is cluster type, it represents memory size of per sharding."
  type        = number
}

variable "name" {
  description = "(optional) - Instance name."
  type        = string
  default     = null
}

variable "password" {
  description = "(required) - Password for a Redis user, which should be 8 to 16 characters."
  type        = string
}

variable "port" {
  description = "(optional) - The port used to access a redis instance. The default value is 6379. And this value can't be changed after creation, or the Redis instance will be recreated."
  type        = number
  default     = null
}

variable "prepaid_period" {
  description = "(optional) - The tenancy (time unit is month) of the prepaid instance, NOTE: it only works when charge_type is set to `PREPAID`. Valid values are `1`, `2`, `3`, `4`, `5`, `6`, `7`, `8`, `9`, `10`, `11`, `12`, `24`, `36`."
  type        = number
  default     = null
}

variable "project_id" {
  description = "(optional) - Specifies which project the instance should belong to."
  type        = number
  default     = null
}

variable "redis_replicas_num" {
  description = "(optional) - The number of instance copies. This is not required for standalone and master slave versions."
  type        = number
  default     = null
}

variable "redis_shard_num" {
  description = "(optional) - The number of instance shard. This is not required for standalone and master slave versions."
  type        = number
  default     = null
}

variable "security_groups" {
  description = "(optional) - ID of security group. If both vpc_id and subnet_id are not set, this argument should not be set either."
  type        = set(string)
  default     = null
}

variable "subnet_id" {
  description = "(optional) - Specifies which subnet the instance should belong to."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Instance tags."
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(optional) - Instance type. Available values: `cluster_ckv`,`cluster_redis5.0`,`cluster_redis`,`master_slave_ckv`,`master_slave_redis5.0`,`master_slave_redis`,`standalone_redis`, specific region support specific types, need to refer data `tencentcloud_redis_zone_config`."
  type        = string
  default     = null
}

variable "type_id" {
  description = "(optional) - Instance type. Available values reference data source `tencentcloud_redis_zone_config` or [document](https://intl.cloud.tencent.com/document/product/239/32069)."
  type        = number
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of the vpc with which the instance is to be associated."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_redis_instance" "this" {
  # availability_zone - (required) is a type of string
  availability_zone = var.availability_zone
  # charge_type - (optional) is a type of string
  charge_type = var.charge_type
  # force_delete - (optional) is a type of bool
  force_delete = var.force_delete
  # mem_size - (required) is a type of number
  mem_size = var.mem_size
  # name - (optional) is a type of string
  name = var.name
  # password - (required) is a type of string
  password = var.password
  # port - (optional) is a type of number
  port = var.port
  # prepaid_period - (optional) is a type of number
  prepaid_period = var.prepaid_period
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # redis_replicas_num - (optional) is a type of number
  redis_replicas_num = var.redis_replicas_num
  # redis_shard_num - (optional) is a type of number
  redis_shard_num = var.redis_shard_num
  # security_groups - (optional) is a type of set of string
  security_groups = var.security_groups
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # type - (optional) is a type of string
  type = var.type
  # type_id - (optional) is a type of number
  type_id = var.type_id
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_redis_instance.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_redis_instance.this.id
}

output "ip" {
  description = "returns a string"
  value       = tencentcloud_redis_instance.this.ip
}

output "name" {
  description = "returns a string"
  value       = tencentcloud_redis_instance.this.name
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_redis_instance.this.status
}

output "subnet_id" {
  description = "returns a string"
  value       = tencentcloud_redis_instance.this.subnet_id
}

output "vpc_id" {
  description = "returns a string"
  value       = tencentcloud_redis_instance.this.vpc_id
}

output "this" {
  value = tencentcloud_redis_instance.this
}
```

[top](#index)