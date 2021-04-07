# fastly_tls_certificate

[back](../fastly.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/fastly/d/fastly_tls_certificate"

  # domains - (optional) is a type of set of string
  domains = []
  # issued_to - (optional) is a type of string
  issued_to = null
  # issuer - (optional) is a type of string
  issuer = null
  # name - (optional) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "domains" {
  description = "(optional) - Domains that are listed in any certificates' Subject Alternative Names (SAN) list."
  type        = set(string)
  default     = null
}

variable "issued_to" {
  description = "(optional) - The hostname for which a certificate was issued."
  type        = string
  default     = null
}

variable "issuer" {
  description = "(optional) - The certificate authority that issued the certificate."
  type        = string
  default     = null
}

variable "name" {
  description = "(optional) - Human-readable name used to identify the certificate. Defaults to the certificate's Common Name or first Subject Alternative Name entry."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "fastly_tls_certificate" "this" {
  # domains - (optional) is a type of set of string
  domains = var.domains
  # issued_to - (optional) is a type of string
  issued_to = var.issued_to
  # issuer - (optional) is a type of string
  issuer = var.issuer
  # name - (optional) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.fastly_tls_certificate.this.created_at
}

output "domains" {
  description = "returns a set of string"
  value       = data.fastly_tls_certificate.this.domains
}

output "id" {
  description = "returns a string"
  value       = data.fastly_tls_certificate.this.id
}

output "issued_to" {
  description = "returns a string"
  value       = data.fastly_tls_certificate.this.issued_to
}

output "issuer" {
  description = "returns a string"
  value       = data.fastly_tls_certificate.this.issuer
}

output "name" {
  description = "returns a string"
  value       = data.fastly_tls_certificate.this.name
}

output "replace" {
  description = "returns a bool"
  value       = data.fastly_tls_certificate.this.replace
}

output "serial_number" {
  description = "returns a string"
  value       = data.fastly_tls_certificate.this.serial_number
}

output "signature_algorithm" {
  description = "returns a string"
  value       = data.fastly_tls_certificate.this.signature_algorithm
}

output "updated_at" {
  description = "returns a string"
  value       = data.fastly_tls_certificate.this.updated_at
}

output "this" {
  value = fastly_tls_certificate.this
}
```

[top](#index)