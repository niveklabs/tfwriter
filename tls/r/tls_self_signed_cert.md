# tls_self_signed_cert

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
module "tls_self_signed_cert" {
  source = "./modules/tls/r/tls_self_signed_cert"

  # allowed_uses - (required) is a type of list of string
  allowed_uses = []
  # dns_names - (optional) is a type of list of string
  dns_names = []
  # early_renewal_hours - (optional) is a type of number
  early_renewal_hours = null
  # ip_addresses - (optional) is a type of list of string
  ip_addresses = []
  # is_ca_certificate - (optional) is a type of bool
  is_ca_certificate = null
  # key_algorithm - (required) is a type of string
  key_algorithm = null
  # private_key_pem - (required) is a type of string
  private_key_pem = null
  # set_subject_key_id - (optional) is a type of bool
  set_subject_key_id = null
  # uris - (optional) is a type of list of string
  uris = []
  # validity_period_hours - (required) is a type of number
  validity_period_hours = null

  subject = [{
    common_name         = null
    country             = null
    locality            = null
    organization        = null
    organizational_unit = null
    postal_code         = null
    province            = null
    serial_number       = null
    street_address      = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "allowed_uses" {
  description = "(required) - Uses that are allowed for the certificate"
  type        = list(string)
}

variable "dns_names" {
  description = "(optional) - List of DNS names to use as subjects of the certificate"
  type        = list(string)
  default     = null
}

variable "early_renewal_hours" {
  description = "(optional) - Number of hours before the certificates expiry when a new certificate will be generated"
  type        = number
  default     = null
}

variable "ip_addresses" {
  description = "(optional) - List of IP addresses to use as subjects of the certificate"
  type        = list(string)
  default     = null
}

variable "is_ca_certificate" {
  description = "(optional) - Whether the generated certificate will be usable as a CA certificate"
  type        = bool
  default     = null
}

variable "key_algorithm" {
  description = "(required) - Name of the algorithm to use to generate the certificate's private key"
  type        = string
}

variable "private_key_pem" {
  description = "(required) - PEM-encoded private key that the certificate will belong to"
  type        = string
}

variable "set_subject_key_id" {
  description = "(optional) - If true, the generated certificate will include a subject key identifier."
  type        = bool
  default     = null
}

variable "uris" {
  description = "(optional) - List of URIs to use as subjects of the certificate"
  type        = list(string)
  default     = null
}

variable "validity_period_hours" {
  description = "(required) - Number of hours that the certificate will remain valid for"
  type        = number
}

variable "subject" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      common_name         = string
      country             = string
      locality            = string
      organization        = string
      organizational_unit = string
      postal_code         = string
      province            = string
      serial_number       = string
      street_address      = list(string)
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "tls_self_signed_cert" "this" {
  allowed_uses          = var.allowed_uses
  dns_names             = var.dns_names
  early_renewal_hours   = var.early_renewal_hours
  ip_addresses          = var.ip_addresses
  is_ca_certificate     = var.is_ca_certificate
  key_algorithm         = var.key_algorithm
  private_key_pem       = var.private_key_pem
  set_subject_key_id    = var.set_subject_key_id
  uris                  = var.uris
  validity_period_hours = var.validity_period_hours

  dynamic "subject" {
    for_each = var.subject
    content {
      common_name         = subject.value["common_name"]
      country             = subject.value["country"]
      locality            = subject.value["locality"]
      organization        = subject.value["organization"]
      organizational_unit = subject.value["organizational_unit"]
      postal_code         = subject.value["postal_code"]
      province            = subject.value["province"]
      serial_number       = subject.value["serial_number"]
      street_address      = subject.value["street_address"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cert_pem" {
  description = "returns a string"
  value       = tls_self_signed_cert.this.cert_pem
}

output "id" {
  description = "returns a string"
  value       = tls_self_signed_cert.this.id
}

output "ready_for_renewal" {
  description = "returns a bool"
  value       = tls_self_signed_cert.this.ready_for_renewal
}

output "validity_end_time" {
  description = "returns a string"
  value       = tls_self_signed_cert.this.validity_end_time
}

output "validity_start_time" {
  description = "returns a string"
  value       = tls_self_signed_cert.this.validity_start_time
}

output "this" {
  value = tls_self_signed_cert.this
}
```

[top](#index)