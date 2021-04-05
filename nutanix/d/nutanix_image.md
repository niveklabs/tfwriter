# nutanix_image

[back](../nutanix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nutanix = ">= 1.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nutanix_image" {
  source = "./modules/nutanix/d/nutanix_image"

  # image_id - (optional) is a type of string
  image_id = null
  # image_name - (optional) is a type of string
  image_name = null

  categories = [{
    name  = null
    value = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_name" {
  description = "(optional)"
  type        = string
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

### Datasource

```terraform
data "nutanix_image" "this" {
  image_id   = var.image_id
  image_name = var.image_name

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
  value       = data.nutanix_image.this.api_version
}

output "architecture" {
  description = "returns a string"
  value       = data.nutanix_image.this.architecture
}

output "availability_zone_reference" {
  description = "returns a map of string"
  value       = data.nutanix_image.this.availability_zone_reference
}

output "checksum" {
  description = "returns a map of string"
  value       = data.nutanix_image.this.checksum
}

output "cluster_name" {
  description = "returns a string"
  value       = data.nutanix_image.this.cluster_name
}

output "cluster_uuid" {
  description = "returns a string"
  value       = data.nutanix_image.this.cluster_uuid
}

output "description" {
  description = "returns a string"
  value       = data.nutanix_image.this.description
}

output "id" {
  description = "returns a string"
  value       = data.nutanix_image.this.id
}

output "image_type" {
  description = "returns a string"
  value       = data.nutanix_image.this.image_type
}

output "metadata" {
  description = "returns a map of string"
  value       = data.nutanix_image.this.metadata
}

output "name" {
  description = "returns a string"
  value       = data.nutanix_image.this.name
}

output "owner_reference" {
  description = "returns a map of string"
  value       = data.nutanix_image.this.owner_reference
}

output "project_reference" {
  description = "returns a map of string"
  value       = data.nutanix_image.this.project_reference
}

output "retrieval_uri_list" {
  description = "returns a list of string"
  value       = data.nutanix_image.this.retrieval_uri_list
}

output "size_bytes" {
  description = "returns a number"
  value       = data.nutanix_image.this.size_bytes
}

output "source_uri" {
  description = "returns a string"
  value       = data.nutanix_image.this.source_uri
}

output "state" {
  description = "returns a string"
  value       = data.nutanix_image.this.state
}

output "version" {
  description = "returns a map of string"
  value       = data.nutanix_image.this.version
}

output "this" {
  value = nutanix_image.this
}
```

[top](#index)