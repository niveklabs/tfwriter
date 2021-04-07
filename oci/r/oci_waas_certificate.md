# oci_waas_certificate

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
module "oci_waas_certificate" {
  source = "./modules/oci/r/oci_waas_certificate"

  # certificate_data - (required) is a type of string
  certificate_data = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_trust_verification_disabled - (optional) is a type of bool
  is_trust_verification_disabled = null
  # private_key_data - (required) is a type of string
  private_key_data = null

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
variable "certificate_data" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_trust_verification_disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "private_key_data" {
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
resource "oci_waas_certificate" "this" {
  # certificate_data - (required) is a type of string
  certificate_data = var.certificate_data
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # is_trust_verification_disabled - (optional) is a type of bool
  is_trust_verification_disabled = var.is_trust_verification_disabled
  # private_key_data - (required) is a type of string
  private_key_data = var.private_key_data

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
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
  value       = oci_waas_certificate.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_waas_certificate.this.display_name
}

output "extensions" {
  description = "returns a list of object"
  value       = oci_waas_certificate.this.extensions
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_waas_certificate.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_waas_certificate.this.id
}

output "is_trust_verification_disabled" {
  description = "returns a bool"
  value       = oci_waas_certificate.this.is_trust_verification_disabled
}

output "issued_by" {
  description = "returns a string"
  value       = oci_waas_certificate.this.issued_by
}

output "issuer_name" {
  description = "returns a list of object"
  value       = oci_waas_certificate.this.issuer_name
}

output "public_key_info" {
  description = "returns a list of object"
  value       = oci_waas_certificate.this.public_key_info
}

output "serial_number" {
  description = "returns a string"
  value       = oci_waas_certificate.this.serial_number
}

output "signature_algorithm" {
  description = "returns a string"
  value       = oci_waas_certificate.this.signature_algorithm
}

output "state" {
  description = "returns a string"
  value       = oci_waas_certificate.this.state
}

output "subject_name" {
  description = "returns a list of object"
  value       = oci_waas_certificate.this.subject_name
}

output "time_created" {
  description = "returns a string"
  value       = oci_waas_certificate.this.time_created
}

output "time_not_valid_after" {
  description = "returns a string"
  value       = oci_waas_certificate.this.time_not_valid_after
}

output "time_not_valid_before" {
  description = "returns a string"
  value       = oci_waas_certificate.this.time_not_valid_before
}

output "version" {
  description = "returns a number"
  value       = oci_waas_certificate.this.version
}

output "this" {
  value = oci_waas_certificate.this
}
```

[top](#index)