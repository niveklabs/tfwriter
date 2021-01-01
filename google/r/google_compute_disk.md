# google_compute_disk

[back](../google.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "google_compute_disk" {
  source = "./modules/google/r/google_compute_disk"

  # description - (optional) is a type of string
  description = null
  # image - (optional) is a type of string
  image = null
  # labels - (optional) is a type of map of string
  labels = {}
  # name - (required) is a type of string
  name = null
  # physical_block_size_bytes - (optional) is a type of number
  physical_block_size_bytes = null
  # project - (optional) is a type of string
  project = null
  # size - (optional) is a type of number
  size = null
  # snapshot - (optional) is a type of string
  snapshot = null
  # type - (optional) is a type of string
  type = null
  # zone - (optional) is a type of string
  zone = null

  disk_encryption_key = [{
    kms_key_self_link       = null
    kms_key_service_account = null
    raw_key                 = null
    sha256                  = null
  }]

  source_image_encryption_key = [{
    kms_key_self_link       = null
    kms_key_service_account = null
    raw_key                 = null
    sha256                  = null
  }]

  source_snapshot_encryption_key = [{
    kms_key_self_link       = null
    kms_key_service_account = null
    raw_key                 = null
    sha256                  = null
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

```hcl
variable "description" {
  description = "(optional) - An optional description of this resource. Provide this property when\nyou create the resource."
  type        = string
  default     = null
}

variable "image" {
  description = "(optional) - The image from which to initialize this disk. This can be\none of: the image's 'self_link', 'projects/{project}/global/images/{image}',\n'projects/{project}/global/images/family/{family}', 'global/images/{image}',\n'global/images/family/{family}', 'family/{family}', '{project}/{family}',\n'{project}/{image}', '{family}', or '{image}'. If referred by family, the\nimages names must include the family name. If they don't, use the\n[google_compute_image data source](/docs/providers/google/d/compute_image.html).\nFor instance, the image 'centos-6-v20180104' includes its family name 'centos-6'.\nThese images can be referred by family name here."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels to apply to this disk.  A list of key->value pairs."
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and match\nthe regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means the\nfirst character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the last\ncharacter, which cannot be a dash."
  type        = string
}

variable "physical_block_size_bytes" {
  description = "(optional) - Physical block size of the persistent disk, in bytes. If not present\nin a request, a default value is used. Currently supported sizes\nare 4096 and 16384, other sizes may be added in the future.\nIf an unsupported value is requested, the error message will list\nthe supported values for the caller's project."
  type        = number
  default     = null
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "size" {
  description = "(optional) - Size of the persistent disk, specified in GB. You can specify this\nfield when creating a persistent disk using the 'image' or\n'snapshot' parameter, or specify it alone to create an empty\npersistent disk.\n\nIf you specify this field along with 'image' or 'snapshot',\nthe value must not be less than the size of the image\nor the size of the snapshot."
  type        = number
  default     = null
}

variable "snapshot" {
  description = "(optional) - The source snapshot used to create this disk. You can provide this as\na partial or full URL to the resource. If the snapshot is in another\nproject than this disk, you must supply a full URL. For example, the\nfollowing are valid values:\n\n* 'https://www.googleapis.com/compute/v1/projects/project/global/snapshots/snapshot'\n* 'projects/project/global/snapshots/snapshot'\n* 'global/snapshots/snapshot'\n* 'snapshot'"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - URL of the disk type resource describing which disk type to use to\ncreate the disk. Provide this when creating the disk."
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - A reference to the zone where the disk resides."
  type        = string
  default     = null
}

variable "disk_encryption_key" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
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

variable "source_image_encryption_key" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
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

variable "source_snapshot_encryption_key" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
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

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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

```hcl
resource "google_compute_disk" "this" {
  description               = var.description
  image                     = var.image
  labels                    = var.labels
  name                      = var.name
  physical_block_size_bytes = var.physical_block_size_bytes
  project                   = var.project
  size                      = var.size
  snapshot                  = var.snapshot
  type                      = var.type
  zone                      = var.zone

  dynamic "disk_encryption_key" {
    for_each = var.disk_encryption_key
    content {
      kms_key_self_link       = disk_encryption_key.value["kms_key_self_link"]
      kms_key_service_account = disk_encryption_key.value["kms_key_service_account"]
      raw_key                 = disk_encryption_key.value["raw_key"]
    }
  }

  dynamic "source_image_encryption_key" {
    for_each = var.source_image_encryption_key
    content {
      kms_key_self_link       = source_image_encryption_key.value["kms_key_self_link"]
      kms_key_service_account = source_image_encryption_key.value["kms_key_service_account"]
      raw_key                 = source_image_encryption_key.value["raw_key"]
    }
  }

  dynamic "source_snapshot_encryption_key" {
    for_each = var.source_snapshot_encryption_key
    content {
      kms_key_self_link       = source_snapshot_encryption_key.value["kms_key_self_link"]
      kms_key_service_account = source_snapshot_encryption_key.value["kms_key_service_account"]
      raw_key                 = source_snapshot_encryption_key.value["raw_key"]
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

```hcl
output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_disk.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_disk.this.id
}

output "label_fingerprint" {
  description = "returns a string"
  value       = google_compute_disk.this.label_fingerprint
}

output "last_attach_timestamp" {
  description = "returns a string"
  value       = google_compute_disk.this.last_attach_timestamp
}

output "last_detach_timestamp" {
  description = "returns a string"
  value       = google_compute_disk.this.last_detach_timestamp
}

output "physical_block_size_bytes" {
  description = "returns a number"
  value       = google_compute_disk.this.physical_block_size_bytes
}

output "project" {
  description = "returns a string"
  value       = google_compute_disk.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_disk.this.self_link
}

output "size" {
  description = "returns a number"
  value       = google_compute_disk.this.size
}

output "source_image_id" {
  description = "returns a string"
  value       = google_compute_disk.this.source_image_id
}

output "source_snapshot_id" {
  description = "returns a string"
  value       = google_compute_disk.this.source_snapshot_id
}

output "users" {
  description = "returns a list of string"
  value       = google_compute_disk.this.users
}

output "zone" {
  description = "returns a string"
  value       = google_compute_disk.this.zone
}

output "this" {
  value = google_compute_disk.this
}
```

[top](#index)