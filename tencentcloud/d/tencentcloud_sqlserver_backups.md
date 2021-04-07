# tencentcloud_sqlserver_backups

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
module "tencentcloud_sqlserver_backups" {
  source = "./modules/tencentcloud/d/tencentcloud_sqlserver_backups"

  # end_time - (required) is a type of string
  end_time = null
  # instance_id - (required) is a type of string
  instance_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # start_time - (required) is a type of string
  start_time = null
}
```

[top](#index)

### Variables

```terraform
variable "end_time" {
  description = "(required) - End time of the instance list, like yyyy-MM-dd HH:mm:ss."
  type        = string
}

variable "instance_id" {
  description = "(required) - Instance ID."
  type        = string
}

variable "result_output_file" {
  description = "(optional) - Used to store results."
  type        = string
  default     = null
}

variable "start_time" {
  description = "(required) - Start time of the instance list, like yyyy-MM-dd HH:mm:ss."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_sqlserver_backups" "this" {
  # end_time - (required) is a type of string
  end_time = var.end_time
  # instance_id - (required) is a type of string
  instance_id = var.instance_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # start_time - (required) is a type of string
  start_time = var.start_time
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_sqlserver_backups.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_sqlserver_backups.this.list
}

output "this" {
  value = tencentcloud_sqlserver_backups.this
}
```

[top](#index)