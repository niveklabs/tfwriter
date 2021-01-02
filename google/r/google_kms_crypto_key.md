# google_kms_crypto_key

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_kms_crypto_key" {
  source = "./modules/google/r/google_kms_crypto_key"

  # key_ring - (required) is a type of string
  key_ring = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # purpose - (optional) is a type of string
  purpose = null
  # rotation_period - (optional) is a type of string
  rotation_period = null
  # skip_initial_version_creation - (optional) is a type of bool
  skip_initial_version_creation = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  version_template = [{
    algorithm        = null
    protection_level = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "key_ring" {
  description = "(required) - The KeyRing that this key belongs to.\nFormat: ''projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}''."
  type        = string
}

variable "labels" {
  description = "(optional) - Labels with user-defined metadata to apply to this resource."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The resource name for the CryptoKey."
  type        = string
}

variable "purpose" {
  description = "(optional) - The immutable purpose of this CryptoKey. See the\n[purpose reference](https://cloud.google.com/kms/docs/reference/rest/v1/projects.locations.keyRings.cryptoKeys#CryptoKeyPurpose)\nfor possible inputs. Default value: \"ENCRYPT_DECRYPT\" Possible values: [\"ENCRYPT_DECRYPT\", \"ASYMMETRIC_SIGN\", \"ASYMMETRIC_DECRYPT\"]"
  type        = string
  default     = null
}

variable "rotation_period" {
  description = "(optional) - Every time this period passes, generate a new CryptoKeyVersion and set it as the primary.\nThe first rotation will take place after the specified period. The rotation period has\nthe format of a decimal number with up to 9 fractional digits, followed by the\nletter 's' (seconds). It must be greater than a day (ie, 86400)."
  type        = string
  default     = null
}

variable "skip_initial_version_creation" {
  description = "(optional) - If set to true, the request will create a CryptoKey without any CryptoKeyVersions. \nYou must use the 'google_kms_key_ring_import_job' resource to import the CryptoKeyVersion."
  type        = bool
  default     = null
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

variable "version_template" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      algorithm        = string
      protection_level = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_kms_crypto_key" "this" {
  key_ring                      = var.key_ring
  labels                        = var.labels
  name                          = var.name
  purpose                       = var.purpose
  rotation_period               = var.rotation_period
  skip_initial_version_creation = var.skip_initial_version_creation

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

  dynamic "version_template" {
    for_each = var.version_template
    content {
      algorithm        = version_template.value["algorithm"]
      protection_level = version_template.value["protection_level"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_kms_crypto_key.this.id
}

output "self_link" {
  description = "returns a string"
  value       = google_kms_crypto_key.this.self_link
}

output "this" {
  value = google_kms_crypto_key.this
}
```

[top](#index)