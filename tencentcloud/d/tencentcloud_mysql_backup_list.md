# tencentcloud_mysql_backup_list

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
module "tencentcloud_mysql_backup_list" {
  source = "./modules/tencentcloud/d/tencentcloud_mysql_backup_list"

  # max_number - (optional) is a type of number
  max_number = null
  # mysql_id - (required) is a type of string
  mysql_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "max_number" {
  description = "(optional) - The latest files to list, rang from 1 to 10000. And the default value is `10`."
  type        = number
  default     = null
}

variable "mysql_id" {
  description = "(required) - Instance ID, such as `cdb-c1nl9rpv`. It is identical to the instance ID displayed in the database console page."
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
data "tencentcloud_mysql_backup_list" "this" {
  max_number         = var.max_number
  mysql_id           = var.mysql_id
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_mysql_backup_list.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_mysql_backup_list.this.list
}

output "this" {
  value = tencentcloud_mysql_backup_list.this
}
```

[top](#index)