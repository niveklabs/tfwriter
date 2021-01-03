# nutanix_image

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_image" {
  source = "./modules/nutanix/r/nutanix_image"

  # architecture - (optional) is a type of string
  architecture = null
  # availability_zone_reference - (optional) is a type of map of string
  availability_zone_reference = {}
  # checksum - (optional) is a type of map of string
  checksum = {}
  # description - (optional) is a type of string
  description = null
  # image_type - (optional) is a type of string
  image_type = null
  # name - (required) is a type of string
  name = null
  # owner_reference - (optional) is a type of map of string
  owner_reference = {}
  # project_reference - (optional) is a type of map of string
  project_reference = {}
  # source_path - (optional) is a type of string
  source_path = null
  # source_uri - (optional) is a type of string
  source_uri = null
  # version - (optional) is a type of map of string
  version = {}

  categories = [{
    name  = null
    value = null
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

variable "availability_zone_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "checksum" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "owner_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "project_reference" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "source_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_uri" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "categories" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nutanix_image" "this" {
  architecture                = var.architecture
  availability_zone_reference = var.availability_zone_reference
  checksum                    = var.checksum
  description                 = var.description
  image_type                  = var.image_type
  name                        = var.name
  owner_reference             = var.owner_reference
  project_reference           = var.project_reference
  source_path                 = var.source_path
  source_uri                  = var.source_uri
  version                     = var.version

  dynamic "categories" {
    for_each = var.categories
    content {
      name  = categories.value["name"]
      value = categories.value["value"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "api_version" {
  description = "returns a string"
  value       = nutanix_image.this.api_version
}

output "architecture" {
  description = "returns a string"
  value       = nutanix_image.this.architecture
}

output "availability_zone_reference" {
  description = "returns a map of string"
  value       = nutanix_image.this.availability_zone_reference
}

output "checksum" {
  description = "returns a map of string"
  value       = nutanix_image.this.checksum
}

output "cluster_name" {
  description = "returns a string"
  value       = nutanix_image.this.cluster_name
}

output "cluster_uuid" {
  description = "returns a string"
  value       = nutanix_image.this.cluster_uuid
}

output "description" {
  description = "returns a string"
  value       = nutanix_image.this.description
}

output "id" {
  description = "returns a string"
  value       = nutanix_image.this.id
}

output "image_type" {
  description = "returns a string"
  value       = nutanix_image.this.image_type
}

output "metadata" {
  description = "returns a map of string"
  value       = nutanix_image.this.metadata
}

output "owner_reference" {
  description = "returns a map of string"
  value       = nutanix_image.this.owner_reference
}

output "retrieval_uri_list" {
  description = "returns a list of string"
  value       = nutanix_image.this.retrieval_uri_list
}

output "size_bytes" {
  description = "returns a number"
  value       = nutanix_image.this.size_bytes
}

output "source_path" {
  description = "returns a string"
  value       = nutanix_image.this.source_path
}

output "source_uri" {
  description = "returns a string"
  value       = nutanix_image.this.source_uri
}

output "state" {
  description = "returns a string"
  value       = nutanix_image.this.state
}

output "version" {
  description = "returns a map of string"
  value       = nutanix_image.this.version
}

output "this" {
  value = nutanix_image.this
}
```

[top](#index)