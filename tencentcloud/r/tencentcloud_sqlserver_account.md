# tencentcloud_sqlserver_account

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
module "tencentcloud_sqlserver_account" {
  source = "./modules/tencentcloud/r/tencentcloud_sqlserver_account"

  # instance_id - (required) is a type of string
  instance_id = null
  # is_admin - (optional) is a type of bool
  is_admin = null
  # name - (required) is a type of string
  name = null
  # password - (required) is a type of string
  password = null
  # remark - (optional) is a type of string
  remark = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required) - Instance ID that the account belongs to."
  type        = string
}

variable "is_admin" {
  description = "(optional) - Indicate that the account is root account or not."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the SQL Server account."
  type        = string
}

variable "password" {
  description = "(required) - Password of the SQL Server account."
  type        = string
}

variable "remark" {
  description = "(optional) - Remark of the SQL Server account."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_sqlserver_account" "this" {
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # is_admin - (optional) is a type of bool
  is_admin = var.is_admin
  # name - (required) is a type of string
  name = var.name
  # password - (required) is a type of string
  password = var.password
  # remark - (optional) is a type of string
  remark = var.remark
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_account.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_account.this.id
}

output "status" {
  description = "returns a number"
  value       = tencentcloud_sqlserver_account.this.status
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_sqlserver_account.this.update_time
}

output "this" {
  value = tencentcloud_sqlserver_account.this
}
```

[top](#index)