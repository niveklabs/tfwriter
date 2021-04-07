# tencentcloud_sqlserver_account_db_attachments

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
module "tencentcloud_sqlserver_account_db_attachments" {
  source = "./modules/tencentcloud/d/tencentcloud_sqlserver_account_db_attachments"

  # account_name - (optional) is a type of string
  account_name = null
  # db_name - (optional) is a type of string
  db_name = null
  # instance_id - (required) is a type of string
  instance_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "account_name" {
  description = "(optional) - Name of the SQL Server account to be queried."
  type        = string
  default     = null
}

variable "db_name" {
  description = "(optional) - Name of the DB to be queried."
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required) - SQL Server instance ID that the account belongs to."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_sqlserver_account_db_attachments" "this" {
  # account_name - (optional) is a type of string
  account_name = var.account_name
  # db_name - (optional) is a type of string
  db_name = var.db_name
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_sqlserver_account_db_attachments.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_sqlserver_account_db_attachments.this.list
}

output "this" {
  value = tencentcloud_sqlserver_account_db_attachments.this
}
```

[top](#index)