# fastly_tls_platform_certificate

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
    fastly = ">= 0.28.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fastly_tls_platform_certificate" {
  source = "./modules/fastly/r/fastly_tls_platform_certificate"

  # allow_untrusted_root - (optional) is a type of bool
  allow_untrusted_root = null
  # certificate_body - (required) is a type of string
  certificate_body = null
  # configuration_id - (required) is a type of string
  configuration_id = null
  # intermediates_blob - (required) is a type of string
  intermediates_blob = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_untrusted_root" {
  description = "(optional) - Disable checking whether the root of the certificate chain is trusted. Useful for development purposes to allow use of self-signed CAs. Defaults to false. Write-only on create."
  type        = bool
  default     = null
}

variable "certificate_body" {
  description = "(required) - PEM-formatted certificate."
  type        = string
}

variable "configuration_id" {
  description = "(required) - ID of TLS configuration to be used to terminate TLS traffic."
  type        = string
}

variable "intermediates_blob" {
  description = "(required) - PEM-formatted certificate chain from the `certificate_body` to its root."
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "fastly_tls_platform_certificate" "this" {
  # allow_untrusted_root - (optional) is a type of bool
  allow_untrusted_root = var.allow_untrusted_root
  # certificate_body - (required) is a type of string
  certificate_body = var.certificate_body
  # configuration_id - (required) is a type of string
  configuration_id = var.configuration_id
  # intermediates_blob - (required) is a type of string
  intermediates_blob = var.intermediates_blob
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = fastly_tls_platform_certificate.this.created_at
}

output "domains" {
  description = "returns a set of string"
  value       = fastly_tls_platform_certificate.this.domains
}

output "id" {
  description = "returns a string"
  value       = fastly_tls_platform_certificate.this.id
}

output "not_after" {
  description = "returns a string"
  value       = fastly_tls_platform_certificate.this.not_after
}

output "not_before" {
  description = "returns a string"
  value       = fastly_tls_platform_certificate.this.not_before
}

output "replace" {
  description = "returns a bool"
  value       = fastly_tls_platform_certificate.this.replace
}

output "updated_at" {
  description = "returns a string"
  value       = fastly_tls_platform_certificate.this.updated_at
}

output "this" {
  value = fastly_tls_platform_certificate.this
}
```

[top](#index)