# tencentcloud_postgresql_instances

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
module "tencentcloud_postgresql_instances" {
  source = "./modules/tencentcloud/d/tencentcloud_postgresql_instances"

  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of number
  project_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the postgresql instance to be query."
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - Project ID of the postgresql instance to be query."
  type        = number
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_postgresql_instances" "this" {
  # name - (optional) is a type of string
  name = var.name
  # project_id - (optional) is a type of number
  project_id = var.project_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_postgresql_instances.this.id
}

output "instance_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_postgresql_instances.this.instance_list
}

output "this" {
  value = tencentcloud_postgresql_instances.this
}
```

[top](#index)