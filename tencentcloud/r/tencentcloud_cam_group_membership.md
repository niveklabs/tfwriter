# tencentcloud_cam_group_membership

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
module "tencentcloud_cam_group_membership" {
  source = "./modules/tencentcloud/r/tencentcloud_cam_group_membership"

  # group_id - (required) is a type of string
  group_id = null
  # user_ids - (required) is a type of set of string
  user_ids = []
}
```

[top](#index)

### Variables

```terraform
variable "group_id" {
  description = "(required) - ID of CAM group."
  type        = string
}

variable "user_ids" {
  description = "(required) - ID set of the CAM group members."
  type        = set(string)
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cam_group_membership" "this" {
  # group_id - (required) is a type of string
  group_id = var.group_id
  # user_ids - (required) is a type of set of string
  user_ids = var.user_ids
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = tencentcloud_cam_group_membership.this.id
}

output "this" {
  value = tencentcloud_cam_group_membership.this
}
```

[top](#index)