# oci_artifacts_container_repository

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_artifacts_container_repository" {
  source = "./modules/oci/d/oci_artifacts_container_repository"

  # repository_id - (required) is a type of string
  repository_id = null
}
```

[top](#index)

### Variables

```terraform
variable "repository_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_artifacts_container_repository" "this" {
  repository_id = var.repository_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_repository.this.compartment_id
}

output "created_by" {
  description = "returns a string"
  value       = data.oci_artifacts_container_repository.this.created_by
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_artifacts_container_repository.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_repository.this.id
}

output "image_count" {
  description = "returns a number"
  value       = data.oci_artifacts_container_repository.this.image_count
}

output "is_immutable" {
  description = "returns a bool"
  value       = data.oci_artifacts_container_repository.this.is_immutable
}

output "is_public" {
  description = "returns a bool"
  value       = data.oci_artifacts_container_repository.this.is_public
}

output "layer_count" {
  description = "returns a number"
  value       = data.oci_artifacts_container_repository.this.layer_count
}

output "layers_size_in_bytes" {
  description = "returns a string"
  value       = data.oci_artifacts_container_repository.this.layers_size_in_bytes
}

output "readme" {
  description = "returns a list of object"
  value       = data.oci_artifacts_container_repository.this.readme
}

output "state" {
  description = "returns a string"
  value       = data.oci_artifacts_container_repository.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_artifacts_container_repository.this.time_created
}

output "time_last_pushed" {
  description = "returns a string"
  value       = data.oci_artifacts_container_repository.this.time_last_pushed
}

output "this" {
  value = oci_artifacts_container_repository.this
}
```

[top](#index)