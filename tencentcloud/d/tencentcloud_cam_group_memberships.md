# tencentcloud_cam_group_memberships

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
module "tencentcloud_cam_group_memberships" {
  source = "./modules/tencentcloud/d/tencentcloud_cam_group_memberships"

  # group_id - (optional) is a type of string
  group_id = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(optional) - ID of CAM group to be queried."
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
data "tencentcloud_cam_group_memberships" "this" {
  group_id           = var.group_id
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cam_group_memberships.this.id
}

output "membership_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cam_group_memberships.this.membership_list
}

output "this" {
  value = tencentcloud_cam_group_memberships.this
}
```

[top](#index)