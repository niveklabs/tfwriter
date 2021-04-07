# oci_artifacts_container_image_signature

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
module "oci_artifacts_container_image_signature" {
  source = "./modules/oci/d/oci_artifacts_container_image_signature"

  # image_signature_id - (required) is a type of string
  image_signature_id = null
}
```

[top](#index)

### Variables

```terraform
variable "image_signature_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_artifacts_container_image_signature" "this" {
  # image_signature_id - (required) is a type of string
  image_signature_id = var.image_signature_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signature.this.compartment_id
}

output "created_by" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signature.this.created_by
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signature.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signature.this.id
}

output "image_id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signature.this.image_id
}

output "kms_key_id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signature.this.kms_key_id
}

output "kms_key_version_id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signature.this.kms_key_version_id
}

output "message" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signature.this.message
}

output "signature" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signature.this.signature
}

output "signing_algorithm" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signature.this.signing_algorithm
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signature.this.time_created
}

output "this" {
  value = oci_artifacts_container_image_signature.this
}
```

[top](#index)