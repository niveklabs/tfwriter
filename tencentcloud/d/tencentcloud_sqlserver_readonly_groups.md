# tencentcloud_sqlserver_readonly_groups

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
module "tencentcloud_sqlserver_readonly_groups" {
  source = "./modules/tencentcloud/d/tencentcloud_sqlserver_readonly_groups"

  # master_instance_id - (optional) is a type of string
  master_instance_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "master_instance_id" {
  description = "(optional) - Master SQL Server instance ID."
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
data "tencentcloud_sqlserver_readonly_groups" "this" {
  # master_instance_id - (optional) is a type of string
  master_instance_id = var.master_instance_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_sqlserver_readonly_groups.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_sqlserver_readonly_groups.this.list
}

output "this" {
  value = tencentcloud_sqlserver_readonly_groups.this
}
```

[top](#index)