# tencentcloud_mysql_readonly_instance

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
module "tencentcloud_mysql_readonly_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_mysql_readonly_instance"

  # auto_renew_flag - (optional) is a type of number
  auto_renew_flag = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # instance_name - (required) is a type of string
  instance_name = null
  # intranet_port - (optional) is a type of number
  intranet_port = null
  # master_instance_id - (required) is a type of string
  master_instance_id = null
  # mem_size - (required) is a type of number
  mem_size = null
  # pay_type - (optional) is a type of number
  pay_type = null
  # period - (optional) is a type of number
  period = null
  # prepaid_period - (optional) is a type of number
  prepaid_period = null
  # security_groups - (optional) is a type of set of string
  security_groups = []
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

variable "charge_type" {
  description = "(optional) - Pay type of instance. Valid values:`PREPAID`, `POSTPAID`. Default is `POSTPAID`."
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

variable "intranet_port" {
  description = "(optional) - Public access port. Valid value ranges: [1024~65535]. The default value is `3306`."
  type        = number
  default     = null
}

variable "master_instance_id" {
  description = "(required) - Indicates the master instance ID of recovery instances."
  type        = string
}

variable "mem_size" {
  description = "(required) - Memory size (in MB)."
  type        = number
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

variable "security_groups" {
  description = "(optional) - Security groups to use."
  type        = set(string)
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
resource "tencentcloud_mysql_readonly_instance" "this" {
  auto_renew_flag    = var.auto_renew_flag
  charge_type        = var.charge_type
  force_delete       = var.force_delete
  instance_name      = var.instance_name
  intranet_port      = var.intranet_port
  master_instance_id = var.master_instance_id
  mem_size           = var.mem_size
  pay_type           = var.pay_type
  period             = var.period
  prepaid_period     = var.prepaid_period
  security_groups    = var.security_groups
  subnet_id          = var.subnet_id
  tags               = var.tags
  volume_size        = var.volume_size
  vpc_id             = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_mysql_readonly_instance.this.id
}

output "intranet_ip" {
  description = "returns a string"
  value       = tencentcloud_mysql_readonly_instance.this.intranet_ip
}

output "locked" {
  description = "returns a number"
  value       = tencentcloud_mysql_readonly_instance.this.locked
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_mysql_readonly_instance.this.status
}

output "task_status" {
  description = "returns a number"
  value       = tencentcloud_mysql_readonly_instance.this.task_status
}

output "this" {
  value = tencentcloud_mysql_readonly_instance.this
}
```

[top](#index)