# tencentcloud_cam_group

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
module "tencentcloud_cam_group" {
  source = "./modules/tencentcloud/r/tencentcloud_cam_group"

  # name - (required) is a type of string
  name = null
  # remark - (optional) is a type of string
  remark = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of CAM group."
  type        = string
}

variable "remark" {
  description = "(optional) - Description of the CAM group."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cam_group" "this" {
  # name - (required) is a type of string
  name = var.name
  # remark - (optional) is a type of string
  remark = var.remark
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_cam_group.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cam_group.this.id
}

output "this" {
  value = tencentcloud_cam_group.this
}
```

[top](#index)