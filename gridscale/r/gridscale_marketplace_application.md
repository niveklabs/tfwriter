# gridscale_marketplace_application

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
module "gridscale_marketplace_application" {
  source = "./modules/gridscale/r/gridscale_marketplace_application"

  # category - (required) is a type of string
  category = null
  # meta_advices - (optional) is a type of string
  meta_advices = null
  # meta_author - (optional) is a type of string
  meta_author = null
  # meta_components - (optional) is a type of set of string
  meta_components = []
  # meta_features - (optional) is a type of string
  meta_features = null
  # meta_hints - (optional) is a type of string
  meta_hints = null
  # meta_icon - (optional) is a type of string
  meta_icon = null
  # meta_license - (optional) is a type of string
  meta_license = null
  # meta_os - (optional) is a type of string
  meta_os = null
  # meta_overview - (optional) is a type of string
  meta_overview = null
  # meta_terms_of_use - (optional) is a type of string
  meta_terms_of_use = null
  # name - (required) is a type of string
  name = null
  # object_storage_path - (required) is a type of string
  object_storage_path = null
  # publish - (optional) is a type of bool
  publish = null
  # setup_cores - (required) is a type of number
  setup_cores = null
  # setup_memory - (required) is a type of number
  setup_memory = null
  # setup_storage_capacity - (required) is a type of number
  setup_storage_capacity = null

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
variable "category" {
  description = "(required) - Category of marketplace application. Accepted values: \"CMS\", \"project management\", \"Adminpanel\", \"Collaboration\", \"Cloud Storage\", \"Archiving\""
  type        = string
}

variable "meta_advices" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta_author" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta_components" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "meta_features" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta_hints" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta_icon" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta_license" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta_os" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta_overview" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "meta_terms_of_use" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The human-readable name of the object. It supports the full UTF-8 character set, with a maximum of 64 characters"
  type        = string
}

variable "object_storage_path" {
  description = "(required) - Path to the images for the application, must be in .gz format and started with s3//"
  type        = string
}

variable "publish" {
  description = "(optional) - Whether you want to publish your application or not"
  type        = bool
  default     = null
}

variable "setup_cores" {
  description = "(required) - Number of server's cores"
  type        = number
}

variable "setup_memory" {
  description = "(required) - The capacity of server's memory in GB"
  type        = number
}

variable "setup_storage_capacity" {
  description = "(required) - The capacity of server's storage in GB"
  type        = number
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
resource "gridscale_marketplace_application" "this" {
  category               = var.category
  meta_advices           = var.meta_advices
  meta_author            = var.meta_author
  meta_components        = var.meta_components
  meta_features          = var.meta_features
  meta_hints             = var.meta_hints
  meta_icon              = var.meta_icon
  meta_license           = var.meta_license
  meta_os                = var.meta_os
  meta_overview          = var.meta_overview
  meta_terms_of_use      = var.meta_terms_of_use
  name                   = var.name
  object_storage_path    = var.object_storage_path
  publish                = var.publish
  setup_cores            = var.setup_cores
  setup_memory           = var.setup_memory
  setup_storage_capacity = var.setup_storage_capacity

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
output "change_time" {
  description = "returns a string"
  value       = gridscale_marketplace_application.this.change_time
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_marketplace_application.this.create_time
}

output "id" {
  description = "returns a string"
  value       = gridscale_marketplace_application.this.id
}

output "is_application_owner" {
  description = "returns a bool"
  value       = gridscale_marketplace_application.this.is_application_owner
}

output "is_publish_global" {
  description = "returns a bool"
  value       = gridscale_marketplace_application.this.is_publish_global
}

output "is_publish_global_requested" {
  description = "returns a bool"
  value       = gridscale_marketplace_application.this.is_publish_global_requested
}

output "is_publish_requested" {
  description = "returns a bool"
  value       = gridscale_marketplace_application.this.is_publish_requested
}

output "is_published" {
  description = "returns a bool"
  value       = gridscale_marketplace_application.this.is_published
}

output "publish_global_requested_date" {
  description = "returns a string"
  value       = gridscale_marketplace_application.this.publish_global_requested_date
}

output "publish_requested_date" {
  description = "returns a string"
  value       = gridscale_marketplace_application.this.publish_requested_date
}

output "published_date" {
  description = "returns a string"
  value       = gridscale_marketplace_application.this.published_date
}

output "published_global_date" {
  description = "returns a string"
  value       = gridscale_marketplace_application.this.published_global_date
}

output "status" {
  description = "returns a string"
  value       = gridscale_marketplace_application.this.status
}

output "type" {
  description = "returns a string"
  value       = gridscale_marketplace_application.this.type
}

output "unique_hash" {
  description = "returns a string"
  value       = gridscale_marketplace_application.this.unique_hash
}

output "this" {
  value = gridscale_marketplace_application.this
}
```

[top](#index)