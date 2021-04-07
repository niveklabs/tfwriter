# tencentcloud_as_scaling_groups

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
module "tencentcloud_as_scaling_groups" {
  source = "./modules/tencentcloud/d/tencentcloud_as_scaling_groups"

  # configuration_id - (optional) is a type of string
  configuration_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # scaling_group_id - (optional) is a type of string
  scaling_group_id = null
  # scaling_group_name - (optional) is a type of string
  scaling_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "configuration_id" {
  description = "(optional) - Filter results by launch configuration ID."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "scaling_group_id" {
  description = "(optional) - A specified scaling group ID used to query."
  type        = string
  default     = null
}

variable "scaling_group_name" {
  description = "(optional) - A scaling group name used to query."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Tags used to query."
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_as_scaling_groups" "this" {
  # configuration_id - (optional) is a type of string
  configuration_id = var.configuration_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # scaling_group_id - (optional) is a type of string
  scaling_group_id = var.scaling_group_id
  # scaling_group_name - (optional) is a type of string
  scaling_group_name = var.scaling_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_as_scaling_groups.this.id
}

output "scaling_group_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_as_scaling_groups.this.scaling_group_list
}

output "this" {
  value = tencentcloud_as_scaling_groups.this
}
```

[top](#index)