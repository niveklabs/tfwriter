# tls_locally_signed_cert

[back](../tls.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tls = ">= 3.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tls_locally_signed_cert" {
  source = "./modules/tls/r/tls_locally_signed_cert"

  # allowed_uses - (required) is a type of list of string
  allowed_uses = []
  # ca_cert_pem - (required) is a type of string
  ca_cert_pem = null
  # ca_key_algorithm - (required) is a type of string
  ca_key_algorithm = null
  # ca_private_key_pem - (required) is a type of string
  ca_private_key_pem = null
  # cert_request_pem - (required) is a type of string
  cert_request_pem = null
  # early_renewal_hours - (optional) is a type of number
  early_renewal_hours = null
  # is_ca_certificate - (optional) is a type of bool
  is_ca_certificate = null
  # set_subject_key_id - (optional) is a type of bool
  set_subject_key_id = null
  # validity_period_hours - (required) is a type of number
  validity_period_hours = null
}
```

[top](#index)

### Variables

```terraform
variable "allowed_uses" {
  description = "(required) - Uses that are allowed for the certificate"
  type        = list(string)
}

variable "ca_cert_pem" {
  description = "(required) - PEM-encoded CA certificate"
  type        = string
}

variable "ca_key_algorithm" {
  description = "(required) - Name of the algorithm used to generate the certificate's private key"
  type        = string
}

variable "ca_private_key_pem" {
  description = "(required) - PEM-encoded CA private key used to sign the certificate"
  type        = string
}

variable "cert_request_pem" {
  description = "(required) - PEM-encoded certificate request"
  type        = string
}

variable "early_renewal_hours" {
  description = "(optional) - Number of hours before the certificates expiry when a new certificate will be generated"
  type        = number
  default     = null
}

variable "is_ca_certificate" {
  description = "(optional) - Whether the generated certificate will be usable as a CA certificate"
  type        = bool
  default     = null
}

variable "set_subject_key_id" {
  description = "(optional) - If true, the generated certificate will include a subject key identifier."
  type        = bool
  default     = null
}

variable "validity_period_hours" {
  description = "(required) - Number of hours that the certificate will remain valid for"
  type        = number
}
```

[top](#index)

### Resource

```terraform
resource "tls_locally_signed_cert" "this" {
  allowed_uses          = var.allowed_uses
  ca_cert_pem           = var.ca_cert_pem
  ca_key_algorithm      = var.ca_key_algorithm
  ca_private_key_pem    = var.ca_private_key_pem
  cert_request_pem      = var.cert_request_pem
  early_renewal_hours   = var.early_renewal_hours
  is_ca_certificate     = var.is_ca_certificate
  set_subject_key_id    = var.set_subject_key_id
  validity_period_hours = var.validity_period_hours
}
```

[top](#index)

### Outputs

```terraform
output "cert_pem" {
  description = "returns a string"
  value       = tls_locally_signed_cert.this.cert_pem
}

output "id" {
  description = "returns a string"
  value       = tls_locally_signed_cert.this.id
}

output "ready_for_renewal" {
  description = "returns a bool"
  value       = tls_locally_signed_cert.this.ready_for_renewal
}

output "validity_end_time" {
  description = "returns a string"
  value       = tls_locally_signed_cert.this.validity_end_time
}

output "validity_start_time" {
  description = "returns a string"
  value       = tls_locally_signed_cert.this.validity_start_time
}

output "this" {
  value = tls_locally_signed_cert.this
}
```

[top](#index)