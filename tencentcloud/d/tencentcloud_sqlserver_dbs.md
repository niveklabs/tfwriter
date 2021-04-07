# tencentcloud_sqlserver_dbs

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
module "tencentcloud_sqlserver_dbs" {
  source = "./modules/tencentcloud/d/tencentcloud_sqlserver_dbs"

  # instance_id - (required) is a type of string
  instance_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "instance_id" {
  description = "(required) - SQL Server instance ID which DB belongs to."
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
data "tencentcloud_sqlserver_dbs" "this" {
  instance_id        = var.instance_id
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "db_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_sqlserver_dbs.this.db_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_sqlserver_dbs.this.id
}

output "this" {
  value = tencentcloud_sqlserver_dbs.this
}
```

[top](#index)