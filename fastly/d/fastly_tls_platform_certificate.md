# fastly_tls_platform_certificate

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
module "fastly_tls_platform_certificate" {
  source = "./modules/fastly/d/fastly_tls_platform_certificate"

  # domains - (optional) is a type of set of string
  domains = []
}
```

[top](#index)

### Variables

```terraform
variable "domains" {
  description = "(optional) - Domains that are listed in any certificate's Subject Alternative Names (SAN) list."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "fastly_tls_platform_certificate" "this" {
  domains = var.domains
}
```

[top](#index)

### Outputs

```terraform
output "configuration_id" {
  description = "returns a string"
  value       = data.fastly_tls_platform_certificate.this.configuration_id
}

output "created_at" {
  description = "returns a string"
  value       = data.fastly_tls_platform_certificate.this.created_at
}

output "domains" {
  description = "returns a set of string"
  value       = data.fastly_tls_platform_certificate.this.domains
}

output "id" {
  description = "returns a string"
  value       = data.fastly_tls_platform_certificate.this.id
}

output "not_after" {
  description = "returns a string"
  value       = data.fastly_tls_platform_certificate.this.not_after
}

output "not_before" {
  description = "returns a string"
  value       = data.fastly_tls_platform_certificate.this.not_before
}

output "replace" {
  description = "returns a bool"
  value       = data.fastly_tls_platform_certificate.this.replace
}

output "updated_at" {
  description = "returns a string"
  value       = data.fastly_tls_platform_certificate.this.updated_at
}

output "this" {
  value = fastly_tls_platform_certificate.this
}
```

[top](#index)