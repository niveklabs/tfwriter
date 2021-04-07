# tencentcloud_cam_user_policy_attachments

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
module "tencentcloud_cam_user_policy_attachments" {
  source = "./modules/tencentcloud/d/tencentcloud_cam_user_policy_attachments"

  # create_mode - (optional) is a type of number
  create_mode = null
  # policy_id - (optional) is a type of string
  policy_id = null
  # policy_type - (optional) is a type of string
  policy_type = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # user_id - (required) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "create_mode" {
  description = "(optional) - Mode of Creation of the CAM user policy attachment. `1` means the CAM policy attachment is created by production, and the others indicate syntax strategy ways."
  type        = number
  default     = null
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

variable "user_id" {
  description = "(required) - ID of the attached CAM user to be queried."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_cam_user_policy_attachments" "this" {
  create_mode        = var.create_mode
  policy_id          = var.policy_id
  policy_type        = var.policy_type
  result_output_file = var.result_output_file
  user_id            = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cam_user_policy_attachments.this.id
}

output "user_policy_attachment_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cam_user_policy_attachments.this.user_policy_attachment_list
}

output "this" {
  value = tencentcloud_cam_user_policy_attachments.this
}
```

[top](#index)