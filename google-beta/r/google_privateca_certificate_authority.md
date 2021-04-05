# google_privateca_certificate_authority

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
module "google_privateca_certificate_authority" {
  source = "./modules/google-beta/r/google_privateca_certificate_authority"

  # certificate_authority_id - (required) is a type of string
  certificate_authority_id = null
  # disable_on_delete - (optional) is a type of bool
  disable_on_delete = null
  # gcs_bucket - (optional) is a type of string
  gcs_bucket = null
  # labels - (optional) is a type of map of string
  labels = {}
  # lifetime - (optional) is a type of string
  lifetime = null
  # location - (required) is a type of string
  location = null
  # project - (optional) is a type of string
  project = null
  # tier - (optional) is a type of string
  tier = null
  # type - (optional) is a type of string
  type = null

  config = [{
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

  issuing_options = [{
    include_ca_cert_url    = null
    include_crl_access_url = null
  }]

  key_spec = [{
    algorithm             = null
    cloud_kms_key_version = null
  }]

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
variable "certificate_authority_id" {
  description = "(required) - The user provided Resource ID for this Certificate Authority."
  type        = string
}

variable "disable_on_delete" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "gcs_bucket" {
  description = "(optional) - The name of a Cloud Storage bucket where this CertificateAuthority will publish content,\nsuch as the CA certificate and CRLs. This must be a bucket name, without any prefixes\n(such as 'gs://') or suffixes (such as '.googleapis.com'). For example, to use a bucket named\nmy-bucket, you would simply specify 'my-bucket'. If not specified, a managed bucket will be\ncreated."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels with user-defined metadata.\n\nAn object containing a list of \"key\": value pairs. Example: { \"name\": \"wrench\", \"mass\":\n\"1.3kg\", \"count\": \"3\" }."
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

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tier" {
  description = "(optional) - The Tier of this CertificateAuthority. 'ENTERPRISE' Certificate Authorities track\nserver side certificates issued, and support certificate revocation. For more details,\nplease check the [associated documentation](https://cloud.google.com/certificate-authority-service/docs/tiers). Default value: \"ENTERPRISE\" Possible values: [\"ENTERPRISE\", \"DEVOPS\"]"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - The Type of this CertificateAuthority.\n\n~> **Note:** For 'SUBORDINATE' Certificate Authorities, they need to\nbe manually activated (via Cloud Console of 'gcloud') before they can\nissue certificates. Default value: \"SELF_SIGNED\" Possible values: [\"SELF_SIGNED\", \"SUBORDINATE\"]"
  type        = string
  default     = null
}

variable "config" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
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
}

variable "issuing_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      include_ca_cert_url    = bool
      include_crl_access_url = bool
    }
  ))
  default = []
}

variable "key_spec" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      algorithm             = string
      cloud_kms_key_version = string
    }
  ))
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
resource "google_privateca_certificate_authority" "this" {
  certificate_authority_id = var.certificate_authority_id
  disable_on_delete        = var.disable_on_delete
  gcs_bucket               = var.gcs_bucket
  labels                   = var.labels
  lifetime                 = var.lifetime
  location                 = var.location
  project                  = var.project
  tier                     = var.tier
  type                     = var.type

  dynamic "config" {
    for_each = var.config
    content {

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

  dynamic "issuing_options" {
    for_each = var.issuing_options
    content {
      include_ca_cert_url    = issuing_options.value["include_ca_cert_url"]
      include_crl_access_url = issuing_options.value["include_crl_access_url"]
    }
  }

  dynamic "key_spec" {
    for_each = var.key_spec
    content {
      algorithm             = key_spec.value["algorithm"]
      cloud_kms_key_version = key_spec.value["cloud_kms_key_version"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_urls" {
  description = "returns a list of object"
  value       = google_privateca_certificate_authority.this.access_urls
}

output "create_time" {
  description = "returns a string"
  value       = google_privateca_certificate_authority.this.create_time
}

output "id" {
  description = "returns a string"
  value       = google_privateca_certificate_authority.this.id
}

output "name" {
  description = "returns a string"
  value       = google_privateca_certificate_authority.this.name
}

output "pem_ca_certificates" {
  description = "returns a list of string"
  value       = google_privateca_certificate_authority.this.pem_ca_certificates
}

output "project" {
  description = "returns a string"
  value       = google_privateca_certificate_authority.this.project
}

output "state" {
  description = "returns a string"
  value       = google_privateca_certificate_authority.this.state
}

output "update_time" {
  description = "returns a string"
  value       = google_privateca_certificate_authority.this.update_time
}

output "this" {
  value = google_privateca_certificate_authority.this
}
```

[top](#index)