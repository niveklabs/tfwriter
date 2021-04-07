# tencentcloud_cam_groups

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
module "tencentcloud_cam_groups" {
  source = "./modules/tencentcloud/d/tencentcloud_cam_groups"

  # group_id - (optional) is a type of string
  group_id = null
  # name - (optional) is a type of string
  name = null
  # remark - (optional) is a type of string
  remark = null
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

variable "name" {
  description = "(optional) - Name of the CAM group to be queried."
  type        = string
  default     = null
}

variable "remark" {
  description = "(optional) - Description of the cam group to be queried."
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
data "tencentcloud_cam_groups" "this" {
  group_id           = var.group_id
  name               = var.name
  remark             = var.remark
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "group_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cam_groups.this.group_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cam_groups.this.id
}

output "this" {
  value = tencentcloud_cam_groups.this
}
```

[top](#index)