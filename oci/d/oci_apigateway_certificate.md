# oci_apigateway_certificate

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_apigateway_certificate" {
  source = "./modules/oci/d/oci_apigateway_certificate"

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
data "oci_apigateway_certificate" "this" {
  certificate_id = var.certificate_id
}
```

[top](#index)

### Outputs

```terraform
output "certificate" {
  description = "returns a string"
  value       = data.oci_apigateway_certificate.this.certificate
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_apigateway_certificate.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_apigateway_certificate.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_apigateway_certificate.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_apigateway_certificate.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_apigateway_certificate.this.id
}

output "intermediate_certificates" {
  description = "returns a string"
  value       = data.oci_apigateway_certificate.this.intermediate_certificates
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_apigateway_certificate.this.lifecycle_details
}

output "private_key" {
  description = "returns a string"
  value       = data.oci_apigateway_certificate.this.private_key
  sensitive   = true
}

output "state" {
  description = "returns a string"
  value       = data.oci_apigateway_certificate.this.state
}

output "subject_names" {
  description = "returns a list of string"
  value       = data.oci_apigateway_certificate.this.subject_names
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_apigateway_certificate.this.time_created
}

output "time_not_valid_after" {
  description = "returns a string"
  value       = data.oci_apigateway_certificate.this.time_not_valid_after
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_apigateway_certificate.this.time_updated
}

output "this" {
  value = oci_apigateway_certificate.this
}
```

[top](#index)