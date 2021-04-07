# tencentcloud_cfs_access_groups

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
module "tencentcloud_cfs_access_groups" {
  source = "./modules/tencentcloud/d/tencentcloud_cfs_access_groups"

  # access_group_id - (optional) is a type of string
  access_group_id = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "access_group_id" {
  description = "(optional) - A specified access group ID used to query."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - A access group Name used to query."
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
data "tencentcloud_cfs_access_groups" "this" {
  access_group_id    = var.access_group_id
  name               = var.name
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "access_group_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cfs_access_groups.this.access_group_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cfs_access_groups.this.id
}

output "this" {
  value = tencentcloud_cfs_access_groups.this
}
```

[top](#index)