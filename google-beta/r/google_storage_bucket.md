# google_storage_bucket

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
    google-beta = ">= 3.51.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "google_storage_bucket" {
  source = "./modules/google-beta/r/google_storage_bucket"

  # bucket_policy_only - (optional) is a type of bool
  bucket_policy_only = null
  # default_event_based_hold - (optional) is a type of bool
  default_event_based_hold = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # labels - (optional) is a type of map of string
  labels = {}
  # location - (optional) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # project - (optional) is a type of string
  project = null
  # requester_pays - (optional) is a type of bool
  requester_pays = null
  # storage_class - (optional) is a type of string
  storage_class = null
  # uniform_bucket_level_access - (optional) is a type of bool
  uniform_bucket_level_access = null

  cors = [{
    max_age_seconds = null
    method          = []
    origin          = []
    response_header = []
  }]

  encryption = [{
    default_kms_key_name = null
  }]

  lifecycle_rule = [{
    action = [{
      storage_class = null
      type          = null
    }]
    condition = [{
      age                        = null
      created_before             = null
      custom_time_before         = null
      days_since_custom_time     = null
      days_since_noncurrent_time = null
      matches_storage_class      = []
      noncurrent_time_before     = null
      num_newer_versions         = null
      with_state                 = null
    }]
  }]

  logging = [{
    log_bucket        = null
    log_object_prefix = null
  }]

  retention_policy = [{
    is_locked        = null
    retention_period = null
  }]

  versioning = [{
    enabled = null
  }]

  website = [{
    main_page_suffix = null
    not_found_page   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bucket_policy_only" {
  description = "(optional) - Enables Bucket Policy Only access to a bucket."
  type        = bool
  default     = null
}

variable "default_event_based_hold" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "force_destroy" {
  description = "(optional) - When deleting a bucket, this boolean option will delete all contained objects. If you try to delete a bucket that contains objects, Terraform will fail that run."
  type        = bool
  default     = null
}

variable "labels" {
  description = "(optional) - A set of key/value label pairs to assign to the bucket."
  type        = map(string)
  default     = null
}

variable "location" {
  description = "(optional) - The Google Cloud Storage location"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - The name of the bucket."
  type        = string
}

variable "project" {
  description = "(optional) - The ID of the project in which the resource belongs. If it is not provided, the provider project is used."
  type        = string
  default     = null
}

variable "requester_pays" {
  description = "(optional) - Enables Requester Pays on a storage bucket."
  type        = bool
  default     = null
}

variable "storage_class" {
  description = "(optional) - The Storage Class of the new bucket. Supported values include: STANDARD, MULTI_REGIONAL, REGIONAL, NEARLINE, COLDLINE, ARCHIVE."
  type        = string
  default     = null
}

variable "uniform_bucket_level_access" {
  description = "(optional) - Enables uniform bucket-level access on a bucket."
  type        = bool
  default     = null
}

variable "cors" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      max_age_seconds = number
      method          = list(string)
      origin          = list(string)
      response_header = list(string)
    }
  ))
  default = []
}

variable "encryption" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      default_kms_key_name = string
    }
  ))
  default = []
}

variable "lifecycle_rule" {
  description = "nested block: NestingList, min items: 0, max items: 100"
  type = set(object(
    {
      action = set(object(
        {
          storage_class = string
          type          = string
        }
      ))
      condition = set(object(
        {
          age                        = number
          created_before             = string
          custom_time_before         = string
          days_since_custom_time     = number
          days_since_noncurrent_time = number
          matches_storage_class      = list(string)
          noncurrent_time_before     = string
          num_newer_versions         = number
          with_state                 = string
        }
      ))
    }
  ))
  default = []
}

variable "logging" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      log_bucket        = string
      log_object_prefix = string
    }
  ))
  default = []
}

variable "retention_policy" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      is_locked        = bool
      retention_period = number
    }
  ))
  default = []
}

variable "versioning" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled = bool
    }
  ))
  default = []
}

variable "website" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      main_page_suffix = string
      not_found_page   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "google_storage_bucket" "this" {
  bucket_policy_only          = var.bucket_policy_only
  default_event_based_hold    = var.default_event_based_hold
  force_destroy               = var.force_destroy
  labels                      = var.labels
  location                    = var.location
  name                        = var.name
  project                     = var.project
  requester_pays              = var.requester_pays
  storage_class               = var.storage_class
  uniform_bucket_level_access = var.uniform_bucket_level_access

  dynamic "cors" {
    for_each = var.cors
    content {
      max_age_seconds = cors.value["max_age_seconds"]
      method          = cors.value["method"]
      origin          = cors.value["origin"]
      response_header = cors.value["response_header"]
    }
  }

  dynamic "encryption" {
    for_each = var.encryption
    content {
      default_kms_key_name = encryption.value["default_kms_key_name"]
    }
  }

  dynamic "lifecycle_rule" {
    for_each = var.lifecycle_rule
    content {

      dynamic "action" {
        for_each = lifecycle_rule.value.action
        content {
          storage_class = action.value["storage_class"]
          type          = action.value["type"]
        }
      }

      dynamic "condition" {
        for_each = lifecycle_rule.value.condition
        content {
          age                        = condition.value["age"]
          created_before             = condition.value["created_before"]
          custom_time_before         = condition.value["custom_time_before"]
          days_since_custom_time     = condition.value["days_since_custom_time"]
          days_since_noncurrent_time = condition.value["days_since_noncurrent_time"]
          matches_storage_class      = condition.value["matches_storage_class"]
          noncurrent_time_before     = condition.value["noncurrent_time_before"]
          num_newer_versions         = condition.value["num_newer_versions"]
          with_state                 = condition.value["with_state"]
        }
      }

    }
  }

  dynamic "logging" {
    for_each = var.logging
    content {
      log_bucket        = logging.value["log_bucket"]
      log_object_prefix = logging.value["log_object_prefix"]
    }
  }

  dynamic "retention_policy" {
    for_each = var.retention_policy
    content {
      is_locked        = retention_policy.value["is_locked"]
      retention_period = retention_policy.value["retention_period"]
    }
  }

  dynamic "versioning" {
    for_each = var.versioning
    content {
      enabled = versioning.value["enabled"]
    }
  }

  dynamic "website" {
    for_each = var.website
    content {
      main_page_suffix = website.value["main_page_suffix"]
      not_found_page   = website.value["not_found_page"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bucket_policy_only" {
  description = "returns a bool"
  value       = google_storage_bucket.this.bucket_policy_only
}

output "id" {
  description = "returns a string"
  value       = google_storage_bucket.this.id
}

output "project" {
  description = "returns a string"
  value       = google_storage_bucket.this.project
}

output "self_link" {
  description = "returns a string"
  value       = google_storage_bucket.this.self_link
}

output "uniform_bucket_level_access" {
  description = "returns a bool"
  value       = google_storage_bucket.this.uniform_bucket_level_access
}

output "url" {
  description = "returns a string"
  value       = google_storage_bucket.this.url
}

output "this" {
  value = google_storage_bucket.this
}
```

[top](#index)