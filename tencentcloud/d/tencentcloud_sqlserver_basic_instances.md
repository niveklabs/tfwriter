# tencentcloud_sqlserver_basic_instances

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
module "tencentcloud_sqlserver_basic_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_sqlserver_basic_instances"

  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(optional) - Project ID of the SQL Server basic instance to be query."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional) - Subnet ID of the SQL Server basic instance to be query."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - Vpc ID of the SQL Server basic instance to be query."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_sqlserver_basic_instances" "this" {
  project_id         = var.project_id
  result_output_file = var.result_output_file
  subnet_id          = var.subnet_id
  vpc_id             = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_sqlserver_basic_instances.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_sqlserver_basic_instances.this.instance_list
}

output "this" {
  value = tencentcloud_sqlserver_basic_instances.this
}
```

[top](#index)