# tencentcloud_image

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
module "tencentcloud_image" {
  source = "./modules/tencentcloud/r/tencentcloud_image"

  # data_disk_ids - (optional) is a type of set of string
  data_disk_ids = []
  # force_poweroff - (optional) is a type of bool
  force_poweroff = null
  # image_description - (optional) is a type of string
  image_description = null
  # image_name - (required) is a type of string
  image_name = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # snapshot_ids - (optional) is a type of set of string
  snapshot_ids = []
  # sysprep - (optional) is a type of bool
  sysprep = null
}
```

[top](#index)

### Variables

```terraform
variable "data_disk_ids" {
  description = "(optional) - Cloud disk ID list, When creating a whole machine image based on an instance, specify the data disk ID contained in the image."
  type        = set(string)
  default     = null
}

variable "force_poweroff" {
  description = "(optional) - Set whether to force shutdown during mirroring. The default value is `false`, when set to true, it means that the mirror will be made after shutdown."
  type        = bool
  default     = null
}

variable "image_description" {
  description = "(optional) - Image Description."
  type        = string
  default     = null
}

variable "image_name" {
  description = "(required) - Image name."
  type        = string
}

variable "instance_id" {
  description = "(optional) - Cloud server instance ID."
  type        = string
  default     = null
}

variable "snapshot_ids" {
  description = "(optional) - Cloud disk snapshot ID list; creating a mirror based on a snapshot must include a system disk snapshot. It cannot be passed in simultaneously with InstanceId."
  type        = set(string)
  default     = null
}

variable "sysprep" {
  description = "(optional) - Sysprep function under Windows. When creating a Windows image, you can select true or false to enable or disable the Syspre function."
  type        = bool
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_image" "this" {
  # data_disk_ids - (optional) is a type of set of string
  data_disk_ids = var.data_disk_ids
  # force_poweroff - (optional) is a type of bool
  force_poweroff = var.force_poweroff
  # image_description - (optional) is a type of string
  image_description = var.image_description
  # image_name - (required) is a type of string
  image_name = var.image_name
  # instance_id - (optional) is a type of string
  instance_id = var.instance_id
  # snapshot_ids - (optional) is a type of set of string
  snapshot_ids = var.snapshot_ids
  # sysprep - (optional) is a type of bool
  sysprep = var.sysprep
}
```

[top](#index)

### Outputs

```terraform
output "data_disk_ids" {
  description = "returns a set of string"
  value       = tencentcloud_image.this.data_disk_ids
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_image.this.id
}

output "this" {
  value = tencentcloud_image.this
}
```

[top](#index)