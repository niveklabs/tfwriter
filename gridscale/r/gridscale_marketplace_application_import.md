# gridscale_marketplace_application_import

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_marketplace_application_import" {
  source = "./modules/gridscale/r/gridscale_marketplace_application_import"

  # import_unique_hash - (required) is a type of string
  import_unique_hash = null

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
variable "import_unique_hash" {
  description = "(required) - Hash of a specific marketplace application that you want to import"
  type        = string
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
resource "gridscale_marketplace_application_import" "this" {
  import_unique_hash = var.import_unique_hash

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
output "category" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.category
}

output "change_time" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.create_time
}

output "id" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.id
}

output "is_application_owner" {
  description = "returns a bool"
  value       = gridscale_marketplace_application_import.this.is_application_owner
}

output "is_publish_global" {
  description = "returns a bool"
  value       = gridscale_marketplace_application_import.this.is_publish_global
}

output "is_publish_global_requested" {
  description = "returns a bool"
  value       = gridscale_marketplace_application_import.this.is_publish_global_requested
}

output "is_publish_requested" {
  description = "returns a bool"
  value       = gridscale_marketplace_application_import.this.is_publish_requested
}

output "is_published" {
  description = "returns a bool"
  value       = gridscale_marketplace_application_import.this.is_published
}

output "meta_advices" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.meta_advices
}

output "meta_author" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.meta_author
}

output "meta_components" {
  description = "returns a set of string"
  value       = gridscale_marketplace_application_import.this.meta_components
}

output "meta_features" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.meta_features
}

output "meta_hints" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.meta_hints
}

output "meta_icon" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.meta_icon
}

output "meta_license" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.meta_license
}

output "meta_os" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.meta_os
}

output "meta_overview" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.meta_overview
}

output "meta_terms_of_use" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.meta_terms_of_use
}

output "name" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.name
}

output "object_storage_path" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.object_storage_path
}

output "publish_global_requested_date" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.publish_global_requested_date
}

output "publish_requested_date" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.publish_requested_date
}

output "published_date" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.published_date
}

output "published_global_date" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.published_global_date
}

output "setup_cores" {
  description = "returns a number"
  value       = gridscale_marketplace_application_import.this.setup_cores
}

output "setup_memory" {
  description = "returns a number"
  value       = gridscale_marketplace_application_import.this.setup_memory
}

output "setup_storage_capacity" {
  description = "returns a number"
  value       = gridscale_marketplace_application_import.this.setup_storage_capacity
}

output "status" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.status
}

output "type" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.type
}

output "unique_hash" {
  description = "returns a string"
  value       = gridscale_marketplace_application_import.this.unique_hash
}

output "this" {
  value = gridscale_marketplace_application_import.this
}
```

[top](#index)