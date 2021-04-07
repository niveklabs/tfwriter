# tencentcloud_cam_user

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
module "tencentcloud_cam_user" {
  source = "./modules/tencentcloud/r/tencentcloud_cam_user"

  # console_login - (optional) is a type of bool
  console_login = null
  # country_code - (optional) is a type of string
  country_code = null
  # email - (optional) is a type of string
  email = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # name - (required) is a type of string
  name = null
  # need_reset_password - (optional) is a type of bool
  need_reset_password = null
  # password - (optional) is a type of string
  password = null
  # phone_num - (optional) is a type of string
  phone_num = null
  # remark - (optional) is a type of string
  remark = null
  # use_api - (optional) is a type of bool
  use_api = null
}
```

[top](#index)

### Variables

```terraform
variable "console_login" {
  description = "(optional) - Indicate whether the CAM user can login to the web console or not."
  type        = bool
  default     = null
}

variable "country_code" {
  description = "(optional) - Country code of the phone number, for example: '86'."
  type        = string
  default     = null
}

variable "email" {
  description = "(optional) - Email of the CAM user."
  type        = string
  default     = null
}

variable "force_delete" {
  description = "(optional) - Indicate whether to force deletes the CAM user. If set false, the API secret key will be checked and failed when exists; otherwise the user will be deleted directly. Default is false."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the CAM user."
  type        = string
}

variable "need_reset_password" {
  description = "(optional) - Indicate whether the CAM user need to reset the password when first logins."
  type        = bool
  default     = null
}

variable "password" {
  description = "(optional) - The password of the CAM user. Password should be at least 8 characters and no more than 32 characters, includes uppercase letters, lowercase letters, numbers and special characters. Only required when `console_login` is true. If not set, a random password will be automatically generated."
  type        = string
  default     = null
}

variable "phone_num" {
  description = "(optional) - Phone number of the CAM user."
  type        = string
  default     = null
}

variable "remark" {
  description = "(optional) - Remark of the CAM user."
  type        = string
  default     = null
}

variable "use_api" {
  description = "(optional) - Indicate whether to generate the API secret key or not."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cam_user" "this" {
  console_login       = var.console_login
  country_code        = var.country_code
  email               = var.email
  force_delete        = var.force_delete
  name                = var.name
  need_reset_password = var.need_reset_password
  password            = var.password
  phone_num           = var.phone_num
  remark              = var.remark
  use_api             = var.use_api
}
```

[top](#index)

### Outputs

```terraform
output "country_code" {
  description = "returns a string"
  value       = tencentcloud_cam_user.this.country_code
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cam_user.this.id
}

output "password" {
  description = "returns a string"
  value       = tencentcloud_cam_user.this.password
  sensitive   = true
}

output "secret_id" {
  description = "returns a string"
  value       = tencentcloud_cam_user.this.secret_id
  sensitive   = true
}

output "secret_key" {
  description = "returns a string"
  value       = tencentcloud_cam_user.this.secret_key
  sensitive   = true
}

output "uid" {
  description = "returns a number"
  value       = tencentcloud_cam_user.this.uid
}

output "uin" {
  description = "returns a number"
  value       = tencentcloud_cam_user.this.uin
}

output "this" {
  value = tencentcloud_cam_user.this
}
```

[top](#index)