# google_healthcare_consent_store

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
    google = ">= 3.63.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_healthcare_consent_store" {
  source = "./modules/google/r/google_healthcare_consent_store"

  # dataset - (required) is a type of string
  dataset = null
  # default_consent_ttl - (optional) is a type of string
  default_consent_ttl = null
  # enable_consent_create_on_update - (optional) is a type of bool
  enable_consent_create_on_update = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null

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
variable "dataset" {
  description = "(required) - Identifies the dataset addressed by this request. Must be in the format\n'projects/{project}/locations/{location}/datasets/{dataset}'"
  type        = string
}

variable "default_consent_ttl" {
  description = "(optional) - Default time to live for consents in this store. Must be at least 24 hours. Updating this field will not affect the expiration time of existing consents.\n\nA duration in seconds with up to nine fractional digits, terminated by 's'. Example: \"3.5s\"."
  type        = string
  default     = null
}

variable "enable_consent_create_on_update" {
  description = "(optional) - If true, [consents.patch] [google.cloud.healthcare.v1.consent.UpdateConsent] creates the consent if it does not already exist."
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - User-supplied key-value pairs used to organize Consent stores.\n\nLabel keys must be between 1 and 63 characters long, have a UTF-8 encoding of maximum 128 bytes, and must\nconform to the following PCRE regular expression: '[\\p{Ll}\\p{Lo}][\\p{Ll}\\p{Lo}\\p{N}_-]{0,62}'\n\nLabel values are optional, must be between 1 and 63 characters long, have a UTF-8 encoding of maximum 128\nbytes, and must conform to the following PCRE regular expression: '[\\p{Ll}\\p{Lo}\\p{N}_-]{0,63}'\n\nNo more than 64 labels can be associated with a given store.\n\nAn object containing a list of \"key\": value pairs.\nExample: { \"name\": \"wrench\", \"mass\": \"1.3kg\", \"count\": \"3\" }."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - The name of this ConsentStore, for example:\n\"consent1\""
  type        = string
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
resource "google_healthcare_consent_store" "this" {
  # dataset - (required) is a type of string
  dataset = var.dataset
  # default_consent_ttl - (optional) is a type of string
  default_consent_ttl = var.default_consent_ttl
  # enable_consent_create_on_update - (optional) is a type of bool
  enable_consent_create_on_update = var.enable_consent_create_on_update
  # labels - (optional) is a type of map of string
  labels = var.labels
  # name - (required) is a type of string
  name = var.name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = google_healthcare_consent_store.this.id
}

output "this" {
  value = google_healthcare_consent_store.this
}
```

[top](#index)