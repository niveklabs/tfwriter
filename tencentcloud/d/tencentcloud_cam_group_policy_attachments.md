# tencentcloud_cam_group_policy_attachments

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
module "tencentcloud_cam_group_policy_attachments" {
  source = "./modules/tencentcloud/d/tencentcloud_cam_group_policy_attachments"

  # create_mode - (optional) is a type of number
  create_mode = null
  # group_id - (required) is a type of string
  group_id = null
  # policy_id - (optional) is a type of string
  policy_id = null
  # policy_type - (optional) is a type of string
  policy_type = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
}
```

[top](#index)

### Variables

```terraform
variable "create_mode" {
  description = "(optional) - Mode of creation of the CAM user policy attachment. 1 means the cam policy attachment is created by production, and the others indicate syntax strategy ways."
  type        = number
  default     = null
}

variable "group_id" {
  description = "(required) - ID of the attached CAM group to be queried."
  type        = string
}

variable "policy_id" {
  description = "(optional) - ID of CAM policy to be queried."
  type        = string
  default     = null
}

variable "policy_type" {
  description = "(optional) - Type of the policy strategy. 'User' means customer strategy and 'QCS' means preset strategy."
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
data "tencentcloud_cam_group_policy_attachments" "this" {
  # create_mode - (optional) is a type of number
  create_mode = var.create_mode
  # group_id - (required) is a type of string
  group_id = var.group_id
  # policy_id - (optional) is a type of string
  policy_id = var.policy_id
  # policy_type - (optional) is a type of string
  policy_type = var.policy_type
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
}
```

[top](#index)

### Outputs

```terraform
output "group_policy_attachment_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cam_group_policy_attachments.this.group_policy_attachment_list
}

output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cam_group_policy_attachments.this.id
}

output "this" {
  value = tencentcloud_cam_group_policy_attachments.this
}
```

[top](#index)