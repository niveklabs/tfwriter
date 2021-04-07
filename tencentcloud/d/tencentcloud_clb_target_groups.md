# tencentcloud_clb_target_groups

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
module "tencentcloud_clb_target_groups" {
  source = "./modules/tencentcloud/d/tencentcloud_clb_target_groups"

  # result_output_file - (optional) is a type of string
  result_output_file = null
  # target_group_id - (optional) is a type of string
  target_group_id = null
  # target_group_name - (optional) is a type of string
  target_group_name = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
}
```

[top](#index)

### Variables

```terraform
variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "target_group_id" {
  description = "(optional) - ID of Target group. Mutually exclusive with `vpc_id` and `target_group_name`. `target_group_id` is preferred."
  type        = string
  default     = null
}

variable "target_group_name" {
  description = "(optional) - Name of target group. Mutually exclusive with `target_group_id`. `target_group_id` is preferred."
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional) - Target group VPC ID. Mutually exclusive with `target_group_id`. `target_group_id` is preferred."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_clb_target_groups" "this" {
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # target_group_id - (optional) is a type of string
  target_group_id = var.target_group_id
  # target_group_name - (optional) is a type of string
  target_group_name = var.target_group_name
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_clb_target_groups.this.id
}

output "list" {
  description = "returns a list of object"
  value       = data.tencentcloud_clb_target_groups.this.list
}

output "this" {
  value = tencentcloud_clb_target_groups.this
}
```

[top](#index)