# oci_artifacts_container_image_signature

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_artifacts_container_image_signature" {
  source = "./modules/oci/r/oci_artifacts_container_image_signature"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # image_id - (required) is a type of string
  image_id = null
  # kms_key_id - (required) is a type of string
  kms_key_id = null
  # kms_key_version_id - (required) is a type of string
  kms_key_version_id = null
  # message - (required) is a type of string
  message = null
  # signature - (required) is a type of string
  signature = null
  # signing_algorithm - (required) is a type of string
  signing_algorithm = null

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

variable "image_id" {
  description = "(required)"
  type        = string
}

variable "kms_key_id" {
  description = "(required)"
  type        = string
}

variable "kms_key_version_id" {
  description = "(required)"
  type        = string
}

variable "message" {
  description = "(required)"
  type        = string
}

variable "signature" {
  description = "(required)"
  type        = string
}

variable "signing_algorithm" {
  description = "(required)"
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
resource "oci_artifacts_container_image_signature" "this" {
  compartment_id     = var.compartment_id
  image_id           = var.image_id
  kms_key_id         = var.kms_key_id
  kms_key_version_id = var.kms_key_version_id
  message            = var.message
  signature          = var.signature
  signing_algorithm  = var.signing_algorithm

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
  value       = oci_artifacts_container_image_signature.this.created_by
}

output "display_name" {
  description = "returns a string"
  value       = oci_artifacts_container_image_signature.this.display_name
}

output "id" {
  description = "returns a string"
  value       = oci_artifacts_container_image_signature.this.id
}

output "time_created" {
  description = "returns a string"
  value       = oci_artifacts_container_image_signature.this.time_created
}

output "this" {
  value = oci_artifacts_container_image_signature.this
}
```

[top](#index)