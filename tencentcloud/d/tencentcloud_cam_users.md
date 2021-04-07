# tencentcloud_cam_users

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
module "tencentcloud_cam_users" {
  source = "./modules/tencentcloud/d/tencentcloud_cam_users"

  # console_login - (optional) is a type of bool
  console_login = null
  # country_code - (optional) is a type of string
  country_code = null
  # email - (optional) is a type of string
  email = null
  # name - (optional) is a type of string
  name = null
  # phone_num - (optional) is a type of string
  phone_num = null
  # remark - (optional) is a type of string
  remark = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # uid - (optional) is a type of number
  uid = null
  # uin - (optional) is a type of number
  uin = null
}
```

[top](#index)

### Variables

```terraform
variable "console_login" {
  description = "(optional) - Indicate whether the user can login in."
  type        = bool
  default     = null
}

variable "country_code" {
  description = "(optional) - Country code of the CAM user to be queried."
  type        = string
  default     = null
}

variable "email" {
  description = "(optional) - Email of the CAM user to be queried."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of CAM user to be queried."
  type        = string
  default     = null
}

variable "phone_num" {
  description = "(optional) - Phone num of the CAM user to be queried."
  type        = string
  default     = null
}

variable "remark" {
  description = "(optional) - Remark of the CAM user to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "uid" {
  description = "(optional) - Uid of the CAM user to be queried."
  type        = number
  default     = null
}

variable "uin" {
  description = "(optional) - Uin of the CAM user to be queried."
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_cam_users" "this" {
  # console_login - (optional) is a type of bool
  console_login = var.console_login
  # country_code - (optional) is a type of string
  country_code = var.country_code
  # email - (optional) is a type of string
  email = var.email
  # name - (optional) is a type of string
  name = var.name
  # phone_num - (optional) is a type of string
  phone_num = var.phone_num
  # remark - (optional) is a type of string
  remark = var.remark
  # result_output_file - (optional) is a type of string
  result_output_file = var.result_output_file
  # uid - (optional) is a type of number
  uid = var.uid
  # uin - (optional) is a type of number
  uin = var.uin
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cam_users.this.id
}

output "user_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cam_users.this.user_list
}

output "this" {
  value = tencentcloud_cam_users.this
}
```

[top](#index)