# fastly_tls_certificate

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fastly = ">= 0.27.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_tls_certificate" {
  source = "./modules/fastly/r/fastly_tls_certificate"

  # certificate_body - (required) is a type of string
  certificate_body = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "certificate_body" {
  description = "(required) - PEM-formatted certificate."
  type        = string
}

variable "name" {
  description = "(optional) - Human-readable name used to identify the certificate. Defaults to the certificate's Common Name or first Subject Alternative Name entry."
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fastly_tls_certificate" "this" {
  # certificate_body - (required) is a type of string
  certificate_body = var.certificate_body
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = fastly_tls_certificate.this.created_at
}

output "domains" {
  description = "returns a set of string"
  value       = fastly_tls_certificate.this.domains
}

output "id" {
  description = "returns a string"
  value       = fastly_tls_certificate.this.id
}

output "issued_to" {
  description = "returns a string"
  value       = fastly_tls_certificate.this.issued_to
}

output "issuer" {
  description = "returns a string"
  value       = fastly_tls_certificate.this.issuer
}

output "name" {
  description = "returns a string"
  value       = fastly_tls_certificate.this.name
}

output "replace" {
  description = "returns a bool"
  value       = fastly_tls_certificate.this.replace
}

output "serial_number" {
  description = "returns a string"
  value       = fastly_tls_certificate.this.serial_number
}

output "signature_algorithm" {
  description = "returns a string"
  value       = fastly_tls_certificate.this.signature_algorithm
}

output "updated_at" {
  description = "returns a string"
  value       = fastly_tls_certificate.this.updated_at
}

output "this" {
  value = fastly_tls_certificate.this
}
```

[top](#index)