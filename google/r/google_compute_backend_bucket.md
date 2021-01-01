# google_compute_backend_bucket

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
module "google_compute_backend_bucket" {
  source = "./modules/google/r/google_compute_backend_bucket"

  # bucket_name - (required) is a type of string
  bucket_name = null
  # description - (optional) is a type of string
  description = null
  # enable_cdn - (optional) is a type of bool
  enable_cdn = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null

  cdn_policy = [{
    signed_url_cache_max_age_sec = null
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
variable "bucket_name" {
  description = "(required) - Cloud Storage bucket name."
  type        = string
}

variable "description" {
  description = "(optional) - An optional textual description of the resource; provided by the\nclient when the resource is created."
  type        = string
  default     = null
}

variable "enable_cdn" {
  description = "(optional) - If true, enable Cloud CDN for this BackendBucket."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Name of the resource. Provided by the client when the resource is\ncreated. The name must be 1-63 characters long, and comply with\nRFC1035.  Specifically, the name must be 1-63 characters long and\nmatch the regular expression '[a-z]([-a-z0-9]*[a-z0-9])?' which means\nthe first character must be a lowercase letter, and all following\ncharacters must be a dash, lowercase letter, or digit, except the\nlast character, which cannot be a dash."
  type        = string
}

variable "project" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cdn_policy" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      signed_url_cache_max_age_sec = number
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
resource "google_compute_backend_bucket" "this" {
  bucket_name = var.bucket_name
  description = var.description
  enable_cdn  = var.enable_cdn
  name        = var.name
  project     = var.project

  dynamic "cdn_policy" {
    for_each = var.cdn_policy
    content {
      signed_url_cache_max_age_sec = cdn_policy.value["signed_url_cache_max_age_sec"]
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
  value       = google_compute_backend_bucket.this.creation_timestamp
}

output "id" {
  description = "returns a string"
  value       = google_compute_backend_bucket.this.id
}

output "project" {
  description = "returns a string"
  value       = google_compute_backend_bucket.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_compute_backend_bucket.this.self_link
}

output "this" {
  value = google_compute_backend_bucket.this
}
```

[top](#index)