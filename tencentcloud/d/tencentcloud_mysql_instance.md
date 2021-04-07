# tencentcloud_mysql_instance

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/tencentcloud/d/tencentcloud_mysql_instance"

  # charge_type - (optional) is a type of string
  charge_type = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # init_flag - (optional) is a type of number
  init_flag = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # instance_role - (optional) is a type of string
  instance_role = null
  # limit - (optional) is a type of number
  limit = null
  # mysql_id - (optional) is a type of string
  mysql_id = null
  # offset - (optional) is a type of number
  offset = null
  # pay_type - (optional) is a type of number
  pay_type = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # status - (optional) is a type of number
  status = null
  # with_dr - (optional) is a type of number
  with_dr = null
  # with_master - (optional) is a type of number
  with_master = null
  # with_ro - (optional) is a type of number
  with_ro = null
}
```

[top](#index)

### Variables

```terraform
variable "charge_type" {
  description = "(optional) - Pay type of instance, valid values are `PREPAID` and `POSTPAID`."
  type        = string
  default     = null
}

variable "engine_version" {
  description = "(optional) - The version number of the database engine to use. Supported versions include 5.5/5.6/5.7/8.0."
  type        = string
  default     = null
}

variable "init_flag" {
  description = "(optional) - Initialization mark. Available values: `0` - Uninitialized; `1` - Initialized."
  type        = number
  default     = null
}

variable "instance_name" {
  description = "(optional) - Name of mysql instance."
  type        = string
  default     = null
}

variable "instance_role" {
  description = "(optional) - Instance type. Supported values include: `master` - master instance, `dr` - disaster recovery instance, and `ro` - read-only instance."
  type        = string
  default     = null
}

variable "limit" {
  description = "(optional) - Number of results returned for a single request. Default is `20`, and maximum is 2000."
  type        = number
  default     = null
}

variable "mysql_id" {
  description = "(optional) - Instance ID, such as `cdb-c1nl9rpv`. It is identical to the instance ID displayed in the database console page."
  type        = string
  default     = null
}

variable "offset" {
  description = "(optional) - Record offset. Default is 0."
  type        = number
  default     = null
}

variable "pay_type" {
  description = "(optional) - Pay type of instance, `0`: prepay, `1`: postpaid."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional) - Security groups ID of instance."
  type        = string
  default     = null
}

variable "status" {
  description = "(optional) - Instance status. Available values: `0` - Creating; `1` - Running; `4` - Isolating; `5` - Isolated."
  type        = number
  default     = null
}

variable "with_dr" {
  description = "(optional) - Indicates whether to query disaster recovery instances."
  type        = number
  default     = null
}

variable "with_master" {
  description = "(optional) - Indicates whether to query master instances."
  type        = number
  default     = null
}

variable "with_ro" {
  description = "(optional) - Indicates whether to query read-only instances."
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_mysql_instance" "this" {
  charge_type        = var.charge_type
  engine_version     = var.engine_version
  init_flag          = var.init_flag
  instance_name      = var.instance_name
  instance_role      = var.instance_role
  limit              = var.limit
  mysql_id           = var.mysql_id
  offset             = var.offset
  pay_type           = var.pay_type
  result_output_file = var.result_output_file
  security_group_id  = var.security_group_id
  status             = var.status
  with_dr            = var.with_dr
  with_master        = var.with_master
  with_ro            = var.with_ro
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_mysql_instance.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_mysql_instance.this.instance_list
}

output "this" {
  value = tencentcloud_mysql_instance.this
}
```

[top](#index)