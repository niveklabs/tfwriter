# alicloud_image_import

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.120.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_image_import" {
  source = "./modules/alicloud/r/alicloud_image_import"

  # architecture - (optional) is a type of string
  architecture = null
  # description - (optional) is a type of string
  description = null
  # image_name - (optional) is a type of string
  image_name = null
  # license_type - (optional) is a type of string
  license_type = null
  # os_type - (optional) is a type of string
  os_type = null
  # platform - (optional) is a type of string
  platform = null

  disk_device_mapping = [{
    device          = null
    disk_image_size = null
    format          = null
    oss_bucket      = null
    oss_object      = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "architecture" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "license_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "platform" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disk_device_mapping" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      device          = string
      disk_image_size = number
      format          = string
      oss_bucket      = string
      oss_object      = string
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_image_import" "this" {
  # architecture - (optional) is a type of string
  architecture = var.architecture
  # description - (optional) is a type of string
  description = var.description
  # image_name - (optional) is a type of string
  image_name = var.image_name
  # license_type - (optional) is a type of string
  license_type = var.license_type
  # os_type - (optional) is a type of string
  os_type = var.os_type
  # platform - (optional) is a type of string
  platform = var.platform

  dynamic "disk_device_mapping" {
    for_each = var.disk_device_mapping
    content {
      # device - (optional) is a type of string
      device = disk_device_mapping.value["device"]
      # disk_image_size - (optional) is a type of number
      disk_image_size = disk_device_mapping.value["disk_image_size"]
      # format - (optional) is a type of string
      format = disk_device_mapping.value["format"]
      # oss_bucket - (optional) is a type of string
      oss_bucket = disk_device_mapping.value["oss_bucket"]
      # oss_object - (optional) is a type of string
      oss_object = disk_device_mapping.value["oss_object"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_image_import.this.id
}

output "this" {
  value = alicloud_image_import.this
}
```

[top](#index)