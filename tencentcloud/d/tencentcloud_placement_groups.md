# tencentcloud_placement_groups

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
module "tencentcloud_placement_groups" {
  source = "./modules/tencentcloud/d/tencentcloud_placement_groups"

  # name - (optional) is a type of string
  name = null
  # placement_group_id - (optional) is a type of string
  placement_group_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the placement group to be queried."
  type        = string
  default     = null
}

variable "placement_group_id" {
  description = "(optional) - ID of the placement group to be queried."
  type        = string
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
data "tencentcloud_placement_groups" "this" {
  # name - (optional) is a type of string
  name = var.name
  # placement_group_id - (optional) is a type of string
  placement_group_id = var.placement_group_id
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_placement_groups.this.id
}

output "placement_group_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_placement_groups.this.placement_group_list
}

output "this" {
  value = tencentcloud_placement_groups.this
}
```

[top](#index)