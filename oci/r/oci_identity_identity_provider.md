# oci_identity_identity_provider

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
module "oci_identity_identity_provider" {
  source = "./modules/oci/r/oci_identity_identity_provider"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (required) is a type of string
  description = null
  # freeform_attributes - (optional) is a type of map of string
  freeform_attributes = {}
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # metadata - (required) is a type of string
  metadata = null
  # metadata_url - (required) is a type of string
  metadata_url = null
  # name - (required) is a type of string
  name = null
  # product_type - (required) is a type of string
  product_type = null
  # protocol - (required) is a type of string
  protocol = null

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

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "description" {
  description = "(required)"
  type        = string
}

variable "freeform_attributes" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "metadata" {
  description = "(required)"
  type        = string
}

variable "metadata_url" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "product_type" {
  description = "(required)"
  type        = string
}

variable "protocol" {
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
resource "oci_identity_identity_provider" "this" {
  compartment_id      = var.compartment_id
  defined_tags        = var.defined_tags
  description         = var.description
  freeform_attributes = var.freeform_attributes
  freeform_tags       = var.freeform_tags
  metadata            = var.metadata
  metadata_url        = var.metadata_url
  name                = var.name
  product_type        = var.product_type
  protocol            = var.protocol

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_identity_identity_provider.this.defined_tags
}

output "freeform_attributes" {
  description = "returns a map of string"
  value       = oci_identity_identity_provider.this.freeform_attributes
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_identity_identity_provider.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_identity_identity_provider.this.id
}

output "inactive_state" {
  description = "returns a string"
  value       = oci_identity_identity_provider.this.inactive_state
}

output "redirect_url" {
  description = "returns a string"
  value       = oci_identity_identity_provider.this.redirect_url
}

output "signing_certificate" {
  description = "returns a string"
  value       = oci_identity_identity_provider.this.signing_certificate
}

output "state" {
  description = "returns a string"
  value       = oci_identity_identity_provider.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_identity_identity_provider.this.time_created
}

output "this" {
  value = oci_identity_identity_provider.this
}
```

[top](#index)