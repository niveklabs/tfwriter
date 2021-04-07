# tencentcloud_sqlserver_basic_instance

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
module "tencentcloud_sqlserver_basic_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_sqlserver_basic_instance"

  # auto_renew - (optional) is a type of number
  auto_renew = null
  # auto_voucher - (optional) is a type of number
  auto_voucher = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # cpu - (required) is a type of number
  cpu = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # machine_type - (required) is a type of string
  machine_type = null
  # maintenance_start_time - (optional) is a type of string
  maintenance_start_time = null
  # maintenance_time_span - (optional) is a type of number
  maintenance_time_span = null
  # maintenance_week_set - (optional) is a type of set of number
  maintenance_week_set = []
  # memory - (required) is a type of number
  memory = null
  # name - (required) is a type of string
  name = null
  # period - (optional) is a type of number
  period = null
  # project_id - (optional) is a type of number
  project_id = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
  # storage - (required) is a type of number
  storage = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # voucher_ids - (optional) is a type of set of string
  voucher_ids = []
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "auto_renew" {
  description = "(optional) - Automatic renewal sign. 0 for normal renewal, 1 for automatic renewal, the default is 1 automatic renewal. Only valid when purchasing a prepaid instance."
  type        = number
  default     = null
}

variable "auto_voucher" {
  description = "(optional) - Whether to use the voucher automatically; 1 for yes, 0 for no, the default is 0."
  type        = number
  default     = null
}

variable "availability_zone" {
  description = "(optional) - Availability zone."
  type        = string
  default     = null
}

variable "charge_type" {
  description = "(optional) - Pay type of the SQL Server basic instance. For now, only `POSTPAID_BY_HOUR` is valid."
  type        = string
  default     = null
}

variable "cpu" {
  description = "(required) - The CPU number of the SQL Server basic instance."
  type        = number
}

variable "engine_version" {
  description = "(optional) - Version of the SQL Server basic database engine. Allowed values are `2008R2`(SQL Server 2008 Enterprise), `2012SP3`(SQL Server 2012 Enterprise), `2016SP1` (SQL Server 2016 Enterprise), `201602`(SQL Server 2016 Standard) and `2017`(SQL Server 2017 Enterprise). Default is `2008R2`."
  type        = string
  default     = null
}

variable "machine_type" {
  description = "(required) - The host type of the purchased instance, `CLOUD_PREMIUM` for virtual machine high-performance cloud disk, `CLOUD_SSD` for virtual machine SSD cloud disk."
  type        = string
}

variable "maintenance_start_time" {
  description = "(optional) - Start time of the maintenance in one day, format like `HH:mm`."
  type        = string
  default     = null
}

variable "maintenance_time_span" {
  description = "(optional) - The timespan of maintenance in one day, unit is hour."
  type        = number
  default     = null
}

variable "maintenance_week_set" {
  description = "(optional) - A list of integer indicates weekly maintenance. For example, [1,7] presents do weekly maintenance on every Monday and Sunday."
  type        = set(number)
  default     = null
}

variable "memory" {
  description = "(required) - Memory size (in GB). Allowed value must be larger than `memory` that data source `tencentcloud_sqlserver_specinfos` provides."
  type        = number
}

variable "name" {
  description = "(required) - Name of the SQL Server basic instance."
  type        = string
}

variable "period" {
  description = "(optional) - Purchase instance period, the default value is 1, which means one month. The value does not exceed 48."
  type        = number
  default     = null
}

variable "project_id" {
  description = "(optional) - Project ID, default value is 0."
  type        = number
  default     = null
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
  description = "(optional) - The tags of the SQL Server basic instance."
  type        = map(string)
  default     = null
}

variable "voucher_ids" {
  description = "(optional) - An array of voucher IDs, currently only one can be used for a single order."
  type        = set(string)
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
resource "tencentcloud_sqlserver_basic_instance" "this" {
  # auto_renew - (optional) is a type of number
  auto_renew = var.auto_renew
  # auto_voucher - (optional) is a type of number
  auto_voucher = var.auto_voucher
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # charge_type - (optional) is a type of string
  charge_type = var.charge_type
  # cpu - (required) is a type of number
  cpu = var.cpu
  # engine_version - (optional) is a type of string
  engine_version = var.engine_version
  # machine_type - (required) is a type of string
  machine_type = var.machine_type
  # maintenance_start_time - (optional) is a type of string
  maintenance_start_time = var.maintenance_start_time
  # maintenance_time_span - (optional) is a type of number
  maintenance_time_span = var.maintenance_time_span
  # maintenance_week_set - (optional) is a type of set of number
  maintenance_week_set = var.maintenance_week_set
  # memory - (required) is a type of number
  memory = var.memory
  # name - (required) is a type of string
  name = var.name
  # period - (optional) is a type of number
  period = var.period
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # security_groups - (optional) is a type of set of string
  security_groups = var.security_groups
  # storage - (required) is a type of number
  storage = var.storage
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # voucher_ids - (optional) is a type of set of string
  voucher_ids = var.voucher_ids
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_zone" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_basic_instance.this.availability_zone
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_basic_instance.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_basic_instance.this.id
}

output "maintenance_start_time" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_basic_instance.this.maintenance_start_time
}

output "maintenance_time_span" {
  description = "returns a number"
  value       = tencentcloud_sqlserver_basic_instance.this.maintenance_time_span
}

output "maintenance_week_set" {
  description = "returns a set of number"
  value       = tencentcloud_sqlserver_basic_instance.this.maintenance_week_set
}

output "project_id" {
  description = "returns a number"
  value       = tencentcloud_sqlserver_basic_instance.this.project_id
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_sqlserver_basic_instance.this.status
}

output "vip" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_basic_instance.this.vip
}

output "vport" {
  description = "returns a number"
  value       = tencentcloud_sqlserver_basic_instance.this.vport
}

output "this" {
  value = tencentcloud_sqlserver_basic_instance.this
}
```

[top](#index)