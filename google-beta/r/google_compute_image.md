# google_compute_image

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
    google-beta = ">= 3.62.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_compute_image" {
  source = "./modules/google-beta/r/google_compute_image"

  # description - (optional) is a type of string
  description = null
  # disk_size_gb - (optional) is a type of number
  disk_size_gb = null
  # family - (optional) is a type of string
  family = null
  # labels - (optional) is a type of map of string
  labels = {}
  # licenses - (optional) is a type of list of string
  licenses = []
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # source_disk - (optional) is a type of string
  source_disk = null
  # source_image - (optional) is a type of string
  source_image = null
  # source_snapshot - (optional) is a type of string
  source_snapshot = null

  guest_os_features = [{
    type = null
  }]

  raw_disk = [{
    container_type = null
    sha1           = null
    source         = null
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
  description = "(optional) - An optional description of this resource. Provide this property when\nyou create the resource."
  type        = string
  default     = null
}

variable "disk_size_gb" {
  description = "(optional) - Size of the image when restored onto a persistent disk (in GB)."
  type        = number
  default     = null
}

variable "family" {
  description = "(optional) - The name of the image family to which this image belongs. You can\ncreate disks by specifying an image family instead of a specific\nimage name. The image family always returns its latest image that is\nnot deprecated. The name of the image family must comply with\nRFC1035."
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels to apply to this Image."
  type        = map(string)
  default     = null
}

variable "licenses" {
  description = "(optional) - Any applicable license URI."
  type        = list(string)
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource; provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035. Specifically, the name must be 1-63 characters long and\nmatch the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means\nthe first character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the\nlast character, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_disk" {
  description = "(optional) - The source disk to create this image based on.\nYou must provide either this property or the\nrawDisk.source property but not both to create an image."
  type        = string
  default     = null
}

variable "source_image" {
  description = "(optional) - URL of the source image used to create this image. In order to create an image, you must provide the full or partial\nURL of one of the following:\n\n* The selfLink URL\n* This property\n* The rawDisk.source URL\n* The sourceDisk URL"
  type        = string
  default     = null
}

variable "source_snapshot" {
  description = "(optional) - URL of the source snapshot used to create this image.\n\nIn order to create an image, you must provide the full or partial URL of one of the following:\n\n* The selfLink URL\n* This property\n* The sourceImage URL\n* The rawDisk.source URL\n* The sourceDisk URL"
  type        = string
  default     = null
}

variable "guest_os_features" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      type = string
    }
  ))
  default = []
}

variable "raw_disk" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      container_type = string
      sha1           = string
      source         = string
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
resource "google_compute_image" "this" {
  description     = var.description
  disk_size_gb    = var.disk_size_gb
  family          = var.family
  labels          = var.labels
  licenses        = var.licenses
  name            = var.name
  project         = var.project
  source_disk     = var.source_disk
  source_image    = var.source_image
  source_snapshot = var.source_snapshot

  dynamic "guest_os_features" {
    for_each = var.guest_os_features
    content {
      type = guest_os_features.value["type"]
    }
  }

  dynamic "raw_disk" {
    for_each = var.raw_disk
    content {
      container_type = raw_disk.value["container_type"]
      sha1           = raw_disk.value["sha1"]
      source         = raw_disk.value["source"]
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
output "archive_size_bytes" {
  description = "returns a number"
  value       = google_compute_image.this.archive_size_bytes
}

output "creation_timestamp" {
  description = "returns a string"
  value       = google_compute_image.this.creation_timestamp
}

output "disk_size_gb" {
  description = "returns a number"
  value       = google_compute_image.this.disk_size_gb
}

output "id" {
  description = "returns a string"
  value       = google_compute_image.this.id
}

output "label_fingerprint" {
  description = "returns a string"
  value       = google_compute_image.this.label_fingerprint
}

output "licenses" {
  description = "returns a list of string"
  value       = google_compute_image.this.licenses
}

output "project" {
  description = "returns a string"
  value       = google_compute_image.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_image.this.self_link
}

output "this" {
  value = google_compute_image.this
}
```

[top](#index)