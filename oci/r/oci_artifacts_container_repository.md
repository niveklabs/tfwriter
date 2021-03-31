# oci_artifacts_container_repository

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_artifacts_container_repository" {
  source = "./modules/oci/r/oci_artifacts_container_repository"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (required) is a type of string
  display_name = null
  # is_immutable - (optional) is a type of bool
  is_immutable = null
  # is_public - (optional) is a type of bool
  is_public = null

  readme = [{
    content = null
    format  = null
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
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "is_immutable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_public" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "readme" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      content = string
      format  = string
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
resource "oci_artifacts_container_repository" "this" {
  compartment_id = var.compartment_id
  display_name   = var.display_name
  is_immutable   = var.is_immutable
  is_public      = var.is_public

  dynamic "readme" {
    for_each = var.readme
    content {
      content = readme.value["content"]
      format  = readme.value["format"]
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
output "created_by" {
  description = "returns a string"
  value       = oci_artifacts_container_repository.this.created_by
}

output "id" {
  description = "returns a string"
  value       = oci_artifacts_container_repository.this.id
}

output "image_count" {
  description = "returns a number"
  value       = oci_artifacts_container_repository.this.image_count
}

output "is_immutable" {
  description = "returns a bool"
  value       = oci_artifacts_container_repository.this.is_immutable
}

output "is_public" {
  description = "returns a bool"
  value       = oci_artifacts_container_repository.this.is_public
}

output "layer_count" {
  description = "returns a number"
  value       = oci_artifacts_container_repository.this.layer_count
}

output "layers_size_in_bytes" {
  description = "returns a string"
  value       = oci_artifacts_container_repository.this.layers_size_in_bytes
}

output "state" {
  description = "returns a string"
  value       = oci_artifacts_container_repository.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_artifacts_container_repository.this.time_created
}

output "time_last_pushed" {
  description = "returns a string"
  value       = oci_artifacts_container_repository.this.time_last_pushed
}

output "this" {
  value = oci_artifacts_container_repository.this
}
```

[top](#index)