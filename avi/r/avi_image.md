# avi_image

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_image" {
  source = "./modules/avi/r/avi_image"

  # controller_patch_uuid - (optional) is a type of string
  controller_patch_uuid = null
  # name - (optional) is a type of string
  name = null
  # se_patch_uuid - (optional) is a type of string
  se_patch_uuid = null
  # status - (optional) is a type of string
  status = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # type - (optional) is a type of string
  type = null
  # uber_bundle - (optional) is a type of bool
  uber_bundle = null
  # uuid - (optional) is a type of string
  uuid = null

  controller_info = [{
    build = [{
      build_no      = null
      date          = null
      min_version   = null
      patch_version = null
      product       = null
      product_name  = null
      tag           = null
      version       = null
    }]
    hash = null
    patch = [{
      patch_type = null
      reboot     = null
      reboot_list = [{
        patch_version = null
        reboot        = null
      }]
    }]
    path = null
  }]

  migrations = [{
    api_version                        = null
    controller_host_min_free_disk_size = null
    controller_min_free_disk_size      = null
    max_active_versions                = null
    rollback_controller_disk_space     = null
    rollback_se_disk_space             = null
    se_host_min_free_disk_size         = null
    se_min_free_disk_size              = null
    versions                           = []
  }]

  se_info = [{
    build = [{
      build_no      = null
      date          = null
      min_version   = null
      patch_version = null
      product       = null
      product_name  = null
      tag           = null
      version       = null
    }]
    hash = null
    patch = [{
      patch_type = null
      reboot     = null
      reboot_list = [{
        patch_version = null
        reboot        = null
      }]
    }]
    path = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "controller_patch_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "se_patch_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uber_bundle" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "controller_info" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      build = set(object(
        {
          build_no      = number
          date          = string
          min_version   = string
          patch_version = string
          product       = string
          product_name  = string
          tag           = string
          version       = string
        }
      ))
      hash = string
      patch = set(object(
        {
          patch_type = string
          reboot     = bool
          reboot_list = list(object(
            {
              patch_version = string
              reboot        = bool
            }
          ))
        }
      ))
      path = string
    }
  ))
  default = []
}

variable "migrations" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      api_version                        = string
      controller_host_min_free_disk_size = number
      controller_min_free_disk_size      = number
      max_active_versions                = number
      rollback_controller_disk_space     = number
      rollback_se_disk_space             = number
      se_host_min_free_disk_size         = number
      se_min_free_disk_size              = number
      versions                           = list(string)
    }
  ))
  default = []
}

variable "se_info" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      build = set(object(
        {
          build_no      = number
          date          = string
          min_version   = string
          patch_version = string
          product       = string
          product_name  = string
          tag           = string
          version       = string
        }
      ))
      hash = string
      patch = set(object(
        {
          patch_type = string
          reboot     = bool
          reboot_list = list(object(
            {
              patch_version = string
              reboot        = bool
            }
          ))
        }
      ))
      path = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "avi_image" "this" {
  controller_patch_uuid = var.controller_patch_uuid
  name                  = var.name
  se_patch_uuid         = var.se_patch_uuid
  status                = var.status
  tenant_ref            = var.tenant_ref
  type                  = var.type
  uber_bundle           = var.uber_bundle
  uuid                  = var.uuid

  dynamic "controller_info" {
    for_each = var.controller_info
    content {
      hash = controller_info.value["hash"]
      path = controller_info.value["path"]

      dynamic "build" {
        for_each = controller_info.value.build
        content {
          build_no      = build.value["build_no"]
          date          = build.value["date"]
          min_version   = build.value["min_version"]
          patch_version = build.value["patch_version"]
          product       = build.value["product"]
          product_name  = build.value["product_name"]
          tag           = build.value["tag"]
          version       = build.value["version"]
        }
      }

      dynamic "patch" {
        for_each = controller_info.value.patch
        content {
          patch_type = patch.value["patch_type"]
          reboot     = patch.value["reboot"]

          dynamic "reboot_list" {
            for_each = patch.value.reboot_list
            content {
              patch_version = reboot_list.value["patch_version"]
              reboot        = reboot_list.value["reboot"]
            }
          }

        }
      }

    }
  }

  dynamic "migrations" {
    for_each = var.migrations
    content {
      api_version                        = migrations.value["api_version"]
      controller_host_min_free_disk_size = migrations.value["controller_host_min_free_disk_size"]
      controller_min_free_disk_size      = migrations.value["controller_min_free_disk_size"]
      max_active_versions                = migrations.value["max_active_versions"]
      rollback_controller_disk_space     = migrations.value["rollback_controller_disk_space"]
      rollback_se_disk_space             = migrations.value["rollback_se_disk_space"]
      se_host_min_free_disk_size         = migrations.value["se_host_min_free_disk_size"]
      se_min_free_disk_size              = migrations.value["se_min_free_disk_size"]
      versions                           = migrations.value["versions"]
    }
  }

  dynamic "se_info" {
    for_each = var.se_info
    content {
      hash = se_info.value["hash"]
      path = se_info.value["path"]

      dynamic "build" {
        for_each = se_info.value.build
        content {
          build_no      = build.value["build_no"]
          date          = build.value["date"]
          min_version   = build.value["min_version"]
          patch_version = build.value["patch_version"]
          product       = build.value["product"]
          product_name  = build.value["product_name"]
          tag           = build.value["tag"]
          version       = build.value["version"]
        }
      }

      dynamic "patch" {
        for_each = se_info.value.patch
        content {
          patch_type = patch.value["patch_type"]
          reboot     = patch.value["reboot"]

          dynamic "reboot_list" {
            for_each = patch.value.reboot_list
            content {
              patch_version = reboot_list.value["patch_version"]
              reboot        = reboot_list.value["reboot"]
            }
          }

        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "controller_patch_uuid" {
  description = "returns a string"
  value       = avi_image.this.controller_patch_uuid
}

output "id" {
  description = "returns a string"
  value       = avi_image.this.id
}

output "name" {
  description = "returns a string"
  value       = avi_image.this.name
}

output "se_patch_uuid" {
  description = "returns a string"
  value       = avi_image.this.se_patch_uuid
}

output "status" {
  description = "returns a string"
  value       = avi_image.this.status
}

output "tenant_ref" {
  description = "returns a string"
  value       = avi_image.this.tenant_ref
}

output "type" {
  description = "returns a string"
  value       = avi_image.this.type
}

output "uuid" {
  description = "returns a string"
  value       = avi_image.this.uuid
}

output "this" {
  value = avi_image.this
}
```

[top](#index)