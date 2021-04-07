# tencentcloud_cam_user_policy_attachment

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "tencentcloud_cam_user_policy_attachment" {
  source = "./modules/tencentcloud/r/tencentcloud_cam_user_policy_attachment"

  # policy_id - (required) is a type of string
  policy_id = null
  # user_id - (required) is a type of string
  user_id = null
}
```

[top](#index)

### Variables

```terraform
variable "policy_id" {
  description = "(required) - ID of the policy."
  type        = string
}

variable "user_id" {
  description = "(required) - ID of the attached CAM user."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cam_user_policy_attachment" "this" {
  policy_id = var.policy_id
  user_id   = var.user_id
}
```

[top](#index)

### Outputs

```terraform
output "create_mode" {
  description = "returns a number"
  value       = tencentcloud_cam_user_policy_attachment.this.create_mode
}

output "create_time" {
  description = "returns a string"
  value       = tencentcloud_cam_user_policy_attachment.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cam_user_policy_attachment.this.id
}

output "policy_name" {
  description = "returns a string"
  value       = tencentcloud_cam_user_policy_attachment.this.policy_name
}

output "policy_type" {
  description = "returns a string"
  value       = tencentcloud_cam_user_policy_attachment.this.policy_type
}

output "this" {
  value = tencentcloud_cam_user_policy_attachment.this
}
```

[top](#index)