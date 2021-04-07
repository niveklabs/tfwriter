# oci_artifacts_container_images

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_artifacts_container_images" {
  source = "./modules/oci/d/oci_artifacts_container_images"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compartment_id_in_subtree - (optional) is a type of bool
  compartment_id_in_subtree = null
  # display_name - (optional) is a type of string
  display_name = null
  # image_id - (optional) is a type of string
  image_id = null
  # is_versioned - (optional) is a type of bool
  is_versioned = null
  # repository_id - (optional) is a type of string
  repository_id = null
  # repository_name - (optional) is a type of string
  repository_name = null
  # state - (optional) is a type of string
  state = null
  # version - (optional) is a type of string
  version = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "compartment_id_in_subtree" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_versioned" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "repository_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "repository_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_artifacts_container_images" "this" {
  compartment_id            = var.compartment_id
  compartment_id_in_subtree = var.compartment_id_in_subtree
  display_name              = var.display_name
  image_id                  = var.image_id
  is_versioned              = var.is_versioned
  repository_id             = var.repository_id
  repository_name           = var.repository_name
  state                     = var.state
  version                   = var.version

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "container_image_collection" {
  description = "returns a list of object"
  value       = data.oci_artifacts_container_images.this.container_image_collection
}

output "id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_images.this.id
}

output "this" {
  value = oci_artifacts_container_images.this
}
```

[top](#index)