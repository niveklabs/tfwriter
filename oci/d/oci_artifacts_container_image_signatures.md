# oci_artifacts_container_image_signatures

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
module "oci_artifacts_container_image_signatures" {
  source = "./modules/oci/d/oci_artifacts_container_image_signatures"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # compartment_id_in_subtree - (optional) is a type of bool
  compartment_id_in_subtree = null
  # display_name - (optional) is a type of string
  display_name = null
  # image_digest - (optional) is a type of string
  image_digest = null
  # image_id - (optional) is a type of string
  image_id = null
  # kms_key_id - (optional) is a type of string
  kms_key_id = null
  # kms_key_version_id - (optional) is a type of string
  kms_key_version_id = null
  # repository_id - (optional) is a type of string
  repository_id = null
  # repository_name - (optional) is a type of string
  repository_name = null
  # signing_algorithm - (optional) is a type of string
  signing_algorithm = null

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

variable "image_digest" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_key_version_id" {
  description = "(optional)"
  type        = string
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

variable "signing_algorithm" {
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
data "oci_artifacts_container_image_signatures" "this" {
  compartment_id            = var.compartment_id
  compartment_id_in_subtree = var.compartment_id_in_subtree
  display_name              = var.display_name
  image_digest              = var.image_digest
  image_id                  = var.image_id
  kms_key_id                = var.kms_key_id
  kms_key_version_id        = var.kms_key_version_id
  repository_id             = var.repository_id
  repository_name           = var.repository_name
  signing_algorithm         = var.signing_algorithm

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
output "container_image_signature_collection" {
  description = "returns a list of object"
  value       = data.oci_artifacts_container_image_signatures.this.container_image_signature_collection
}

output "id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_image_signatures.this.id
}

output "this" {
  value = oci_artifacts_container_image_signatures.this
}
```

[top](#index)