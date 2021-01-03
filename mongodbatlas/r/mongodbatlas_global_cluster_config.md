# mongodbatlas_global_cluster_config

[back](../mongodbatlas.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mongodbatlas = ">= 0.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mongodbatlas_global_cluster_config" {
  source = "./modules/mongodbatlas/r/mongodbatlas_global_cluster_config"

  # cluster_name - (required) is a type of string
  cluster_name = null
  # project_id - (required) is a type of string
  project_id = null

  custom_zone_mappings = [{
    location = null
    zone     = null
  }]

  managed_namespaces = [{
    collection       = null
    custom_shard_key = null
    db               = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "custom_zone_mappings" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      location = string
      zone     = string
    }
  ))
  default = []
}

variable "managed_namespaces" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      collection       = string
      custom_shard_key = string
      db               = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "mongodbatlas_global_cluster_config" "this" {
  cluster_name = var.cluster_name
  project_id   = var.project_id

  dynamic "custom_zone_mappings" {
    for_each = var.custom_zone_mappings
    content {
      location = custom_zone_mappings.value["location"]
      zone     = custom_zone_mappings.value["zone"]
    }
  }

  dynamic "managed_namespaces" {
    for_each = var.managed_namespaces
    content {
      collection       = managed_namespaces.value["collection"]
      custom_shard_key = managed_namespaces.value["custom_shard_key"]
      db               = managed_namespaces.value["db"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "custom_zone_mapping" {
  description = "returns a map of string"
  value       = mongodbatlas_global_cluster_config.this.custom_zone_mapping
}

output "id" {
  description = "returns a string"
  value       = mongodbatlas_global_cluster_config.this.id
}

output "this" {
  value = mongodbatlas_global_cluster_config.this
}
```

[top](#index)