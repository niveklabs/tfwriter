# oci_waas_certificate

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
module "oci_waas_certificate" {
  source = "./modules/oci/d/oci_waas_certificate"

  # certificate_id - (required) is a type of string
  certificate_id = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_waas_certificate" "this" {
  # certificate_id - (required) is a type of string
  certificate_id = var.certificate_id
}
```

[top](#index)

### Outputs

```terraform
output "certificate_data" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.certificate_data
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_waas_certificate.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.display_name
}

output "extensions" {
  description = "returns a list of object"
  value       = data.oci_waas_certificate.this.extensions
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_waas_certificate.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.id
}

output "is_trust_verification_disabled" {
  description = "returns a bool"
  value       = data.oci_waas_certificate.this.is_trust_verification_disabled
}

output "issued_by" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.issued_by
}

output "issuer_name" {
  description = "returns a list of object"
  value       = data.oci_waas_certificate.this.issuer_name
}

output "private_key_data" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.private_key_data
  sensitive   = true
}

output "public_key_info" {
  description = "returns a list of object"
  value       = data.oci_waas_certificate.this.public_key_info
}

output "serial_number" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.serial_number
}

output "signature_algorithm" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.signature_algorithm
}

output "state" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.state
}

output "subject_name" {
  description = "returns a list of object"
  value       = data.oci_waas_certificate.this.subject_name
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.time_created
}

output "time_not_valid_after" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.time_not_valid_after
}

output "time_not_valid_before" {
  description = "returns a string"
  value       = data.oci_waas_certificate.this.time_not_valid_before
}

output "version" {
  description = "returns a number"
  value       = data.oci_waas_certificate.this.version
}

output "this" {
  value = oci_waas_certificate.this
}
```

[top](#index)