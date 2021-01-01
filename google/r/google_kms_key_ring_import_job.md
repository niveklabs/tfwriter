# google_kms_key_ring_import_job

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    google = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "google_kms_key_ring_import_job" {
  source = "./modules/google/r/google_kms_key_ring_import_job"

  # import_job_id - (required) is a type of string
  import_job_id = null
  # import_method - (required) is a type of string
  import_method = null
  # key_ring - (required) is a type of string
  key_ring = null
  # protection_level - (required) is a type of string
  protection_level = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "import_job_id" {
  description = "(required) - It must be unique within a KeyRing and match the regular expression [a-zA-Z0-9_-]{1,63}"
  type        = string
}

variable "import_method" {
  description = "(required) - The wrapping method to be used for incoming key material. Possible values: [\"RSA_OAEP_3072_SHA1_AES_256\", \"RSA_OAEP_4096_SHA1_AES_256\"]"
  type        = string
}

variable "key_ring" {
  description = "(required) - The KeyRing that this import job belongs to.\nFormat: ''projects/{{project}}/locations/{{location}}/keyRings/{{keyRing}}''."
  type        = string
}

variable "protection_level" {
  description = "(required) - The protection level of the ImportJob. This must match the protectionLevel of the\nversionTemplate on the CryptoKey you attempt to import into. Possible values: [\"SOFTWARE\", \"HSM\", \"EXTERNAL\"]"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_kms_key_ring_import_job" "this" {
  import_job_id    = var.import_job_id
  import_method    = var.import_method
  key_ring         = var.key_ring
  protection_level = var.protection_level

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

```hcl
output "attestation" {
  description = "returns a list of object"
  value       = google_kms_key_ring_import_job.this.attestation
}

output "expire_time" {
  description = "returns a string"
  value       = google_kms_key_ring_import_job.this.expire_time
}

output "id" {
  description = "returns a string"
  value       = google_kms_key_ring_import_job.this.id
}

output "name" {
  description = "returns a string"
  value       = google_kms_key_ring_import_job.this.name
}

output "public_key" {
  description = "returns a list of object"
  value       = google_kms_key_ring_import_job.this.public_key
}

output "state" {
  description = "returns a string"
  value       = google_kms_key_ring_import_job.this.state
}

output "this" {
  value = google_kms_key_ring_import_job.this
}
```

[top](#index)