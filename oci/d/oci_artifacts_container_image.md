# oci_artifacts_container_image

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
module "oci_artifacts_container_image" {
  source = "./modules/oci/d/oci_artifacts_container_image"

  # image_id - (required) is a type of string
  image_id = null
}
```

[top](#index)

### Variables

```terraform
variable "image_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_artifacts_container_image" "this" {
  image_id = var.image_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.compartment_id
}

output "created_by" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.created_by
}

output "digest" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.digest
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.id
}

output "layers" {
  description = "returns a list of object"
  value       = data.oci_artifacts_container_image.this.layers
}

output "layers_size_in_bytes" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.layers_size_in_bytes
}

output "manifest_size_in_bytes" {
  description = "returns a number"
  value       = data.oci_artifacts_container_image.this.manifest_size_in_bytes
}

output "pull_count" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.pull_count
}

output "repository_id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.repository_id
}

output "repository_name" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.repository_name
}

output "state" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.time_created
}

output "time_last_pulled" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.time_last_pulled
}

output "version" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image.this.version
}

output "versions" {
  description = "returns a list of object"
  value       = data.oci_artifacts_container_image.this.versions
}

output "this" {
  value = oci_artifacts_container_image.this
}
```

[top](#index)