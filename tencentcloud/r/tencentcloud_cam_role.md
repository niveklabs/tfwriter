# tencentcloud_cam_role

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
module "tencentcloud_cam_role" {
  source = "./modules/tencentcloud/r/tencentcloud_cam_role"

  # console_login - (optional) is a type of bool
  console_login = null
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
variable "console_login" {
  description = "(optional) - Indicade whether the CAM role can login or not."
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Description of the CAM role."
  type        = string
  default     = null
}

variable "document" {
  description = "(required) - Document of the CAM role. The syntax refers to [CAM POLICY](https://intl.cloud.tencent.com/document/product/598/10604). There are some notes when using this para in terraform: 1. The elements in json claimed supporting two types as `string` and `array` only support type `array`; 2. Terraform does not support the `root` syntax, when appears, it must be replaced with the uin it stands for."
  type        = string
}

variable "name" {
  description = "(required) - Name of CAM role."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cam_role" "this" {
  # console_login - (optional) is a type of bool
  console_login = var.console_login
  # description - (optional) is a type of string
  description = var.description
  # document - (required) is a type of string
  document = var.document
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "create_time" {
  description = "returns a string"
  value       = tencentcloud_cam_role.this.create_time
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cam_role.this.id
}

output "update_time" {
  description = "returns a string"
  value       = tencentcloud_cam_role.this.update_time
}

output "this" {
  value = tencentcloud_cam_role.this
}
```

[top](#index)