# tencentcloud_cam_roles

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
module "tencentcloud_cam_roles" {
  source = "./modules/tencentcloud/d/tencentcloud_cam_roles"

  # description - (optional) is a type of string
  description = null
  # name - (optional) is a type of string
  name = null
  # result_output_file - (optional) is a type of string
  result_output_file = null
  # role_id - (optional) is a type of string
  role_id = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - The description of the CAM role to be queried."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Name of the CAM policy to be queried."
  type        = string
  default     = null
}

variable "result_output_file" {
  description = "(optional) - Used to save results."
  type        = string
  default     = null
}

variable "role_id" {
  description = "(optional) - ID of the CAM role to be queried."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "tencentcloud_cam_roles" "this" {
  description        = var.description
  name               = var.name
  result_output_file = var.result_output_file
  role_id            = var.role_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.tencentcloud_cam_roles.this.id
}

output "role_list" {
  description = "returns a list of object"
  value       = data.tencentcloud_cam_roles.this.role_list
}

output "this" {
  value = tencentcloud_cam_roles.this
}
```

[top](#index)