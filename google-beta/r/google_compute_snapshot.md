# google_compute_snapshot

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
module "google_compute_snapshot" {
  source = "./modules/google-beta/r/google_compute_snapshot"

  # description - (optional) is a type of string
  description = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # source_disk - (required) is a type of string
  source_disk = null
  # storage_locations - (optional) is a type of list of string
  storage_locations = []
  # zone - (optional) is a type of string
  zone = null

  snapshot_encryption_key = [{
    kms_key_self_link       = null
    kms_key_service_account = null
    raw_key                 = null
    sha256                  = null
  }]

  source_disk_encryption_key = [{
    kms_key_service_account = null
    raw_key                 = null
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
variable "description" {
  description = "(optional) - An optional description of this resource."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels to apply to this Snapshot."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource; provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_disk" {
  description = "(required) - A reference to the disk used to create this snapshot."
  type        = string
}

variable "storage_locations" {
  description = "(optional) - Cloud Storage bucket storage location of the snapshot (regional or multi-regional)."
  type        = list(string)
  default     = null
}

variable "zone" {
  description = "(optional) - A reference to the zone where the disk is hosted."
  type        = string
  default     = null
}

variable "snapshot_encryption_key" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kms_key_self_link       = string
      kms_key_service_account = string
      raw_key                 = string
      sha256                  = string
    }
  ))
  default = []
}

variable "source_disk_encryption_key" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kms_key_service_account = string
      raw_key                 = string
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_compute_snapshot" "this" {
  description       = var.description
  labels            = var.labels
  name              = var.name
  project           = var.project
  source_disk       = var.source_disk
  storage_locations = var.storage_locations
  zone              = var.zone

  dynamic "snapshot_encryption_key" {
    for_each = var.snapshot_encryption_key
    content {
      kms_key_self_link       = snapshot_encryption_key.value["kms_key_self_link"]
      kms_key_service_account = snapshot_encryption_key.value["kms_key_service_account"]
      raw_key                 = snapshot_encryption_key.value["raw_key"]
    }
  }

  dynamic "source_disk_encryption_key" {
    for_each = var.source_disk_encryption_key
    content {
      kms_key_service_account = source_disk_encryption_key.value["kms_key_service_account"]
      raw_key                 = source_disk_encryption_key.value["raw_key"]
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
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_snapshot.this.creation_timestamp
}

output "disk_size_gb" {
  description = "returns a number"
  value       = google_compute_snapshot.this.disk_size_gb
}

output "id" {
  description = "returns a string"
  value       = google_compute_snapshot.this.id
}

output "label_fingerprint" {
  description = "returns a string"
  value       = google_compute_snapshot.this.label_fingerprint
}

output "licenses" {
  description = "returns a list of string"
  value       = google_compute_snapshot.this.licenses
}

output "project" {
  description = "returns a string"
  value       = google_compute_snapshot.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_snapshot.this.self_link
}

output "snapshot_id" {
  description = "returns a number"
  value       = google_compute_snapshot.this.snapshot_id
}

output "source_disk_link" {
  description = "returns a string"
  value       = google_compute_snapshot.this.source_disk_link
}

output "storage_bytes" {
  description = "returns a number"
  value       = google_compute_snapshot.this.storage_bytes
}

output "storage_locations" {
  description = "returns a list of string"
  value       = google_compute_snapshot.this.storage_locations
}

output "zone" {
  description = "returns a string"
  value       = google_compute_snapshot.this.zone
}

output "this" {
  value = google_compute_snapshot.this
}
```

[top](#index)