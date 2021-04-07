# tencentcloud_sqlserver_db

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
module "tencentcloud_sqlserver_db" {
  source = "./modules/tencentcloud/r/tencentcloud_sqlserver_db"

  # charset - (optional) is a type of string
  charset = null
  # instance_id - (required) is a type of string
  instance_id = null
  # name - (required) is a type of string
  name = null
  # remark - (optional) is a type of string
  remark = null
}
```

[top](#index)

### Variables

```terraform
variable "charset" {
  description = "(optional) - Character set DB uses. Valid values: `Chinese_PRC_CI_AS`, `Chinese_PRC_CS_AS`, `Chinese_PRC_BIN`, `Chinese_Taiwan_Stroke_CI_AS`, `SQL_Latin1_General_CP1_CI_AS`, and `SQL_Latin1_General_CP1_CS_AS`. Default value is `Chinese_PRC_CI_AS`."
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required) - SQL Server instance ID which DB belongs to."
  type        = string
}

variable "name" {
  description = "(required) - Name of SQL Server DB. The database name must be unique and must be composed of numbers, letters and underlines, and the first one can not be underline."
  type        = string
}

variable "remark" {
  description = "(optional) - Remark of the DB."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_sqlserver_db" "this" {
  charset     = var.charset
  instance_id = var.instance_id
  name        = var.name
  remark      = var.remark
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_db.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_db.this.id
}

output "status" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_db.this.status
}

output "this" {
  value = tencentcloud_sqlserver_db.this
}
```

[top](#index)