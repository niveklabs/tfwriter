# rancher2_etcd_backup

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_etcd_backup" {
  source = "./modules/rancher2/r/rancher2_etcd_backup"

  # annotations - (optional) is a type of map of string
  annotations = {}
  # cluster_id - (required) is a type of string
  cluster_id = null
  # filename - (optional) is a type of string
  filename = null
  # labels - (optional) is a type of map of string
  labels = {}
  # manual - (optional) is a type of bool
  manual = null
  # name - (optional) is a type of string
  name = null
  # namespace_id - (optional) is a type of string
  namespace_id = null

  backup_config = [{
    enabled        = null
    interval_hours = null
    retention      = null
    s3_backup_config = [{
      access_key  = null
      bucket_name = null
      custom_ca   = null
      endpoint    = null
      folder      = null
      region      = null
      secret_key  = null
    }]
    safe_timestamp = null
    timeout        = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "cluster_id" {
  description = "(required)"
  type        = string
}

variable "filename" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "manual" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled        = bool
      interval_hours = number
      retention      = number
      s3_backup_config = list(object(
        {
          access_key  = string
          bucket_name = string
          custom_ca   = string
          endpoint    = string
          folder      = string
          region      = string
          secret_key  = string
        }
      ))
      safe_timestamp = bool
      timeout        = number
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_etcd_backup" "this" {
  annotations  = var.annotations
  cluster_id   = var.cluster_id
  filename     = var.filename
  labels       = var.labels
  manual       = var.manual
  name         = var.name
  namespace_id = var.namespace_id

  dynamic "backup_config" {
    for_each = var.backup_config
    content {
      enabled        = backup_config.value["enabled"]
      interval_hours = backup_config.value["interval_hours"]
      retention      = backup_config.value["retention"]
      safe_timestamp = backup_config.value["safe_timestamp"]
      timeout        = backup_config.value["timeout"]

      dynamic "s3_backup_config" {
        for_each = backup_config.value.s3_backup_config
        content {
          access_key  = s3_backup_config.value["access_key"]
          bucket_name = s3_backup_config.value["bucket_name"]
          custom_ca   = s3_backup_config.value["custom_ca"]
          endpoint    = s3_backup_config.value["endpoint"]
          folder      = s3_backup_config.value["folder"]
          region      = s3_backup_config.value["region"]
          secret_key  = s3_backup_config.value["secret_key"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_etcd_backup.this.annotations
}

output "filename" {
  description = "returns a string"
  value       = rancher2_etcd_backup.this.filename
}

output "id" {
  description = "returns a string"
  value       = rancher2_etcd_backup.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_etcd_backup.this.labels
}

output "name" {
  description = "returns a string"
  value       = rancher2_etcd_backup.this.name
}

output "namespace_id" {
  description = "returns a string"
  value       = rancher2_etcd_backup.this.namespace_id
}

output "this" {
  value = rancher2_etcd_backup.this
}
```

[top](#index)