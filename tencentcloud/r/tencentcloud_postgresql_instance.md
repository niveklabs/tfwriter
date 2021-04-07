# tencentcloud_postgresql_instance

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
module "tencentcloud_postgresql_instance" {
  source = "./modules/tencentcloud/r/tencentcloud_postgresql_instance"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # charge_type - (optional) is a type of string
  charge_type = null
  # charset - (optional) is a type of string
  charset = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # memory - (required) is a type of number
  memory = null
  # name - (required) is a type of string
  name = null
  # project_id - (optional) is a type of number
  project_id = null
  # public_access_switch - (optional) is a type of bool
  public_access_switch = null
  # root_password - (required) is a type of string
  root_password = null
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
  description = "(optional) - Pay type of the postgresql instance. For now, only `POSTPAID_BY_HOUR` is valid."
  type        = string
  default     = null
}

variable "charset" {
  description = "(optional) - Charset of the root account. Valid values are `UTF8`,`LATIN1`."
  type        = string
  default     = null
}

variable "engine_version" {
  description = "(optional) - Version of the postgresql database engine. Valid values: `9.3.5`, `9.5.4`, `10.4`."
  type        = string
  default     = null
}

variable "memory" {
  description = "(required) - Memory size(in GB). Allowed value must be larger than `memory` that data source `tencentcloud_postgresql_specinfos` provides."
  type        = number
}

variable "name" {
  description = "(required) - Name of the postgresql instance."
  type        = string
}

variable "project_id" {
  description = "(optional) - Project id, default value is `0`."
  type        = number
  default     = null
}

variable "public_access_switch" {
  description = "(optional) - Indicates whether to enable the access to an instance from public network or not."
  type        = bool
  default     = null
}

variable "root_password" {
  description = "(required) - Password of root account. This parameter can be specified when you purchase master instances, but it should be ignored when you purchase read-only instances or disaster recovery instances."
  type        = string
}

variable "storage" {
  description = "(required) - Volume size(in GB). Allowed value must be a multiple of 10. The storage must be set with the limit of `storage_min` and `storage_max` which data source `tencentcloud_postgresql_specinfos` provides."
  type        = number
}

variable "subnet_id" {
  description = "(optional) - ID of subnet."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The available tags within this postgresql."
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
resource "tencentcloud_postgresql_instance" "this" {
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # charge_type - (optional) is a type of string
  charge_type = var.charge_type
  # charset - (optional) is a type of string
  charset = var.charset
  # engine_version - (optional) is a type of string
  engine_version = var.engine_version
  # memory - (required) is a type of number
  memory = var.memory
  # name - (required) is a type of string
  name = var.name
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # public_access_switch - (optional) is a type of bool
  public_access_switch = var.public_access_switch
  # root_password - (required) is a type of string
  root_password = var.root_password
  # storage - (required) is a type of number
  storage = var.storage
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "availability_zone" {
  description = "returns a string"
  value       = tencentcloud_postgresql_instance.this.availability_zone
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_postgresql_instance.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_postgresql_instance.this.id
}

output "private_access_ip" {
  description = "returns a string"
  value       = tencentcloud_postgresql_instance.this.private_access_ip
}

output "private_access_port" {
  description = "returns a number"
  value       = tencentcloud_postgresql_instance.this.private_access_port
}

output "public_access_host" {
  description = "returns a string"
  value       = tencentcloud_postgresql_instance.this.public_access_host
}

output "public_access_port" {
  description = "returns a number"
  value       = tencentcloud_postgresql_instance.this.public_access_port
}

output "this" {
  value = tencentcloud_postgresql_instance.this
}
```

[top](#index)