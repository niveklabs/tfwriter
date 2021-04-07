# tencentcloud_cam_policy

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
module "tencentcloud_cam_policy" {
  source = "./modules/tencentcloud/r/tencentcloud_cam_policy"

  # description - (optional) is a type of string
  description = null
  # document - (required) is a type of string
  document = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the CAM policy."
  type        = string
  default     = null
}

variable "document" {
  description = "(required) - Document of the CAM policy. The syntax refers to [CAM POLICY](https://intl.cloud.tencent.com/document/product/598/10604). There are some notes when using this para in terraform: 1. The elements in JSON claimed supporting two types as `string` and `array` only support type `array`; 2. Terraform does not support the `root` syntax, when it appears, it must be replaced with the uin it stands for."
  type        = string
}

variable "name" {
  description = "(required) - Name of CAM policy."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cam_policy" "this" {
  description = var.description
  document    = var.document
  name        = var.name
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_cam_policy.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cam_policy.this.id
}

output "type" {
  description = "returns a number"
  value       = tencentcloud_cam_policy.this.type
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_cam_policy.this.update_time
}

output "this" {
  value = tencentcloud_cam_policy.this
}
```

[top](#index)