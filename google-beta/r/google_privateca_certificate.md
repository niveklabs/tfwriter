# google_privateca_certificate

[back](../google-beta.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google-beta = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_privateca_certificate" {
  source = "./modules/google-beta/r/google_privateca_certificate"

  # certificate_authority - (required) is a type of string
  certificate_authority = null
  # labels - (optional) is a type of map of string
  labels = {}
  # lifetime - (optional) is a type of string
  lifetime = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # pem_csr - (optional) is a type of string
  pem_csr = null
  # project - (optional) is a type of string
  project = null

  config = [{
    public_key = [{
      key  = null
      type = null
    }]
    reusable_config = [{
      reusable_config = null
    }]
    subject_config = [{
      common_name = null
      subject = [{
        country_code        = null
        locality            = null
        organization        = null
        organizational_unit = null
        postal_code         = null
        province            = null
        street_address      = null
      }]
      subject_alt_name = [{
        dns_names       = []
        email_addresses = []
        ip_addresses    = []
        uris            = []
      }]
    }]
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "certificate_authority" {
  description = "(required) - Certificate Authority name."
  type        = string
}

variable "labels" {
  description = "(optional) - Labels with user-defined metadata to apply to this resource."
  type        = map(string)
  default     = null
}

variable "lifetime" {
  description = "(optional) - The desired lifetime of the CA certificate. Used to create the \"notBeforeTime\" and\n\"notAfterTime\" fields inside an X.509 certificate. A duration in seconds with up to nine\nfractional digits, terminated by 's'. Example: \"3.5s\"."
  type        = string
  default     = null
}

variable "location" {
  description = "(required) - Location of the CertificateAuthority. A full list of valid locations can be found by\nrunning 'gcloud beta privateca locations list'."
  type        = string
}

variable "name" {
  description = "(required) - The name for this Certificate ."
  type        = string
}

variable "pem_csr" {
  description = "(optional) - Immutable. A pem-encoded X.509 certificate signing request (CSR)."
  type        = string
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      public_key = list(object(
        {
          key  = string
          type = string
        }
      ))
      reusable_config = list(object(
        {
          reusable_config = string
        }
      ))
      subject_config = list(object(
        {
          common_name = string
          subject = list(object(
            {
              country_code        = string
              locality            = string
              organization        = string
              organizational_unit = string
              postal_code         = string
              province            = string
              street_address      = string
            }
          ))
          subject_alt_name = list(object(
            {
              dns_names       = list(string)
              email_addresses = list(string)
              ip_addresses    = list(string)
              uris            = list(string)
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_privateca_certificate" "this" {
  certificate_authority = var.certificate_authority
  labels                = var.labels
  lifetime              = var.lifetime
  location              = var.location
  name                  = var.name
  pem_csr               = var.pem_csr
  project               = var.project

  dynamic "config" {
    for_each = var.config
    content {

      dynamic "public_key" {
        for_each = config.value.public_key
        content {
          key  = public_key.value["key"]
          type = public_key.value["type"]
        }
      }

      dynamic "reusable_config" {
        for_each = config.value.reusable_config
        content {
          reusable_config = reusable_config.value["reusable_config"]
        }
      }

      dynamic "subject_config" {
        for_each = config.value.subject_config
        content {
          common_name = subject_config.value["common_name"]

          dynamic "subject" {
            for_each = subject_config.value.subject
            content {
              country_code        = subject.value["country_code"]
              locality            = subject.value["locality"]
              organization        = subject.value["organization"]
              organizational_unit = subject.value["organizational_unit"]
              postal_code         = subject.value["postal_code"]
              province            = subject.value["province"]
              street_address      = subject.value["street_address"]
            }
          }

          dynamic "subject_alt_name" {
            for_each = subject_config.value.subject_alt_name
            content {
              dns_names       = subject_alt_name.value["dns_names"]
              email_addresses = subject_alt_name.value["email_addresses"]
              ip_addresses    = subject_alt_name.value["ip_addresses"]
              uris            = subject_alt_name.value["uris"]
            }
          }

        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "certificate_description" {
  description = "returns a list of object"
  value       = google_privateca_certificate.this.certificate_description
}

output "create_time" {
  description = "returns a string"
  value       = google_privateca_certificate.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_privateca_certificate.this.id
}

output "pem_certificate" {
  description = "returns a string"
  value       = google_privateca_certificate.this.pem_certificate
}

output "pem_certificates" {
  description = "returns a list of string"
  value       = google_privateca_certificate.this.pem_certificates
}

output "project" {
  description = "returns a string"
  value       = google_privateca_certificate.this.project
}

output "revocation_details" {
  description = "returns a list of object"
  value       = google_privateca_certificate.this.revocation_details
}

output "update_time" {
  description = "returns a string"
  value       = google_privateca_certificate.this.update_time
}

output "this" {
  value = google_privateca_certificate.this
}
```

[top](#index)