# alicloud_image

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
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_image" {
  source = "./modules/alicloud/r/alicloud_image"

  # architecture - (optional) is a type of string
  architecture = null
  # description - (optional) is a type of string
  description = null
  # force - (optional) is a type of bool
  force = null
  # image_name - (optional) is a type of string
  image_name = null
  # instance_id - (optional) is a type of string
  instance_id = null
  # name - (optional) is a type of string
  name = null
  # platform - (optional) is a type of string
  platform = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  disk_device_mapping = [{
    device      = null
    disk_type   = null
    size        = null
    snapshot_id = null
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

variable "force" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "image_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "platform" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "disk_device_mapping" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      device      = string
      disk_type   = string
      size        = number
      snapshot_id = string
    }
  ))
  default = []
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
resource "alicloud_image" "this" {
  architecture      = var.architecture
  description       = var.description
  force             = var.force
  image_name        = var.image_name
  instance_id       = var.instance_id
  name              = var.name
  platform          = var.platform
  resource_group_id = var.resource_group_id
  snapshot_id       = var.snapshot_id
  tags              = var.tags

  dynamic "disk_device_mapping" {
    for_each = var.disk_device_mapping
    content {
      device      = disk_device_mapping.value["device"]
      disk_type   = disk_device_mapping.value["disk_type"]
      size        = disk_device_mapping.value["size"]
      snapshot_id = disk_device_mapping.value["snapshot_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
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
  value       = alicloud_image.this.id
}

output "image_name" {
  description = "returns a string"
  value       = alicloud_image.this.image_name
}

output "name" {
  description = "returns a string"
  value       = alicloud_image.this.name
}

output "this" {
  value = alicloud_image.this
}
```

[top](#index)