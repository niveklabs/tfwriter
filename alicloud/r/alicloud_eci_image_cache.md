# alicloud_eci_image_cache

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_eci_image_cache" {
  source = "./modules/alicloud/r/alicloud_eci_image_cache"

  # eip_instance_id - (optional) is a type of string
  eip_instance_id = null
  # image_cache_name - (required) is a type of string
  image_cache_name = null
  # image_cache_size - (optional) is a type of number
  image_cache_size = null
  # images - (required) is a type of set of string
  images = []
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # retention_days - (optional) is a type of number
  retention_days = null
  # security_group_id - (required) is a type of string
  security_group_id = null
  # vswitch_id - (required) is a type of string
  vswitch_id = null
  # zone_id - (optional) is a type of string
  zone_id = null

  image_registry_credential = [{
    password  = null
    server    = null
    user_name = null
  }]

  timeouts = [{
    create = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "eip_instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_cache_name" {
  description = "(required)"
  type        = string
}

variable "image_cache_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "images" {
  description = "(required)"
  type        = set(string)
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "retention_days" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "security_group_id" {
  description = "(required)"
  type        = string
}

variable "vswitch_id" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_registry_credential" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      password  = string
      server    = string
      user_name = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_eci_image_cache" "this" {
  eip_instance_id   = var.eip_instance_id
  image_cache_name  = var.image_cache_name
  image_cache_size  = var.image_cache_size
  images            = var.images
  resource_group_id = var.resource_group_id
  retention_days    = var.retention_days
  security_group_id = var.security_group_id
  vswitch_id        = var.vswitch_id
  zone_id           = var.zone_id

  dynamic "image_registry_credential" {
    for_each = var.image_registry_credential
    content {
      password  = image_registry_credential.value["password"]
      server    = image_registry_credential.value["server"]
      user_name = image_registry_credential.value["user_name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "container_group_id" {
  description = "returns a string"
  value       = alicloud_eci_image_cache.this.container_group_id
}

output "id" {
  description = "returns a string"
  value       = alicloud_eci_image_cache.this.id
}

output "status" {
  description = "returns a string"
  value       = alicloud_eci_image_cache.this.status
}

output "this" {
  value = alicloud_eci_image_cache.this
}
```

[top](#index)