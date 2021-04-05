# scaleway_registry_image

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_registry_image" {
  source = "./modules/scaleway/d/scaleway_registry_image"

  # image_id - (optional) is a type of string
  image_id = null
  # name - (optional) is a type of string
  name = null
  # namespace_id - (optional) is a type of string
  namespace_id = null
  # project_id - (optional) is a type of string
  project_id = null
  # region - (optional) is a type of string
  region = null
  # tags - (optional) is a type of list of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "image_id" {
  description = "(optional) - The ID of the registry image"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - The name of the registry image"
  type        = string
  default     = null
}

variable "namespace_id" {
  description = "(optional) - The namespace ID of the registry image"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional) - The region you want to attach the resource to"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The tags associated with the registry image"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_registry_image" "this" {
  image_id     = var.image_id
  name         = var.name
  namespace_id = var.namespace_id
  project_id   = var.project_id
  region       = var.region
  tags         = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.scaleway_registry_image.this.id
}

output "namespace_id" {
  description = "returns a string"
  value       = data.scaleway_registry_image.this.namespace_id
}

output "organization_id" {
  description = "returns a string"
  value       = data.scaleway_registry_image.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = data.scaleway_registry_image.this.project_id
}

output "region" {
  description = "returns a string"
  value       = data.scaleway_registry_image.this.region
}

output "size" {
  description = "returns a number"
  value       = data.scaleway_registry_image.this.size
}

output "tags" {
  description = "returns a list of string"
  value       = data.scaleway_registry_image.this.tags
}

output "visibility" {
  description = "returns a string"
  value       = data.scaleway_registry_image.this.visibility
}

output "this" {
  value = scaleway_registry_image.this
}
```

[top](#index)