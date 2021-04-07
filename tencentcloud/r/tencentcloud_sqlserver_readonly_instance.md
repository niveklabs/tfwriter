# tencentcloud_sqlserver_readonly_instance

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
module "tencentcloud_sqlserver_readonly_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_sqlserver_readonly_instance"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # force_upgrade - (optional) is a type of bool
  force_upgrade = null
  # master_instance_id - (required) is a type of string
  master_instance_id = null
  # memory - (required) is a type of number
  memory = null
  # name - (required) is a type of string
  name = null
  # readonly_group_id - (optional) is a type of string
  readonly_group_id = null
  # readonly_group_type - (required) is a type of number
  readonly_group_type = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # storage - (required) is a type of number
  storage = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional) - Availability zone."
  type        = string
  default     = null
}

variable "charge_type" {
  description = "(optional) - Pay type of the SQL Server instance. For now, only `POSTPAID_BY_HOUR` is valid."
  type        = string
  default     = null
}

variable "force_upgrade" {
  description = "(optional) - Indicate that the master instance upgrade or not. `true` for upgrading the master SQL Server instance to cluster type by force. Default is false. Note: this is not supported with `DUAL`(ha_type), `2017`(engine_version) master SQL Server instance, for it will cause ha_type of the master SQL Server instance change."
  type        = bool
  default     = null
}

variable "master_instance_id" {
  description = "(required) - Indicates the master instance ID of recovery instances."
  type        = string
}

variable "memory" {
  description = "(required) - Memory size (in GB). Allowed value must be larger than `memory` that data source `tencentcloud_sqlserver_specinfos` provides."
  type        = number
}

variable "name" {
  description = "(required) - Name of the SQL Server instance."
  type        = string
}

variable "readonly_group_id" {
  description = "(optional) - ID of the readonly group that this instance belongs to. When `readonly_group_type` set value `3`, it must be set with valid value."
  type        = string
  default     = null
}

variable "readonly_group_type" {
  description = "(required) - Type of readonly group. Valid values: `1`, `3`. `1` for one auto-assigned readonly instance per one readonly group, `2` for creating new readonly group, `3` for all exist readonly instances stay in the exist readonly group. For now, only `1` and `3` are supported."
  type        = number
}

variable "security_groups" {
  description = "(optional) - Security group bound to the instance."
  type        = set(string)
  default     = null
}

variable "storage" {
  description = "(required) - Disk size (in GB). Allowed value must be a multiple of 10. The storage must be set with the limit of `storage_min` and `storage_max` which data source `tencentcloud_sqlserver_specinfos` provides."
  type        = number
}

variable "subnet_id" {
  description = "(optional) - ID of subnet."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The tags of the SQL Server."
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional) - ID of VPC."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_sqlserver_readonly_instance" "this" {
  availability_zone   = var.availability_zone
  charge_type         = var.charge_type
  force_upgrade       = var.force_upgrade
  master_instance_id  = var.master_instance_id
  memory              = var.memory
  name                = var.name
  readonly_group_id   = var.readonly_group_id
  readonly_group_type = var.readonly_group_type
  security_groups     = var.security_groups
  storage             = var.storage
  subnet_id           = var.subnet_id
  tags                = var.tags
  vpc_id              = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_zone" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_readonly_instance.this.availability_zone
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_readonly_instance.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_readonly_instance.this.id
}

output "readonly_group_id" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_readonly_instance.this.readonly_group_id
}

output "ro_flag" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_readonly_instance.this.ro_flag
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_sqlserver_readonly_instance.this.status
}

output "vip" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_readonly_instance.this.vip
}

output "vport" {
  description = "returns a number"
  value       = tencentcloud_sqlserver_readonly_instance.this.vport
}

output "this" {
  value = tencentcloud_sqlserver_readonly_instance.this
}
```

[top](#index)