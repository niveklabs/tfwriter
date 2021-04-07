# tencentcloud_mysql_parameter_list

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
module "tencentcloud_mysql_parameter_list" {
  source = "./modules/tencentcloud/d/tencentcloud_mysql_parameter_list"

  # engine_version - (optional) is a type of string
  engine_version = null
  # mysql_id - (optional) is a type of string
  mysql_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "engine_version" {
  description = "(optional) - The version number of the database engine to use. Supported versions include 5.5/5.6/5.7."
  type        = string
  default     = null
}

variable "mysql_id" {
  description = "(optional) - Instance ID."
  type        = string
  default     = null
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
data "tencentcloud_mysql_parameter_list" "this" {
  engine_version     = var.engine_version
  mysql_id           = var.mysql_id
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_mysql_parameter_list.this.id
}

output "parameter_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_mysql_parameter_list.this.parameter_list
}

output "this" {
  value = tencentcloud_mysql_parameter_list.this
}
```

[top](#index)