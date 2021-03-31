# digitalocean_spaces_bucket

[back](../digitalocean.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    digitalocean = ">= 2.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "digitalocean_spaces_bucket" {
  source = "./modules/digitalocean/r/digitalocean_spaces_bucket"

  # acl - (optional) is a type of string
  acl = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # name - (required) is a type of string
  name = null
  # region - (optional) is a type of string
  region = null

  cors_rule = [{
    allowed_headers = []
    allowed_methods = []
    allowed_origins = []
    max_age_seconds = null
  }]

  lifecycle_rule = [{
    abort_incomplete_multipart_upload_days = null
    enabled                                = null
    expiration = [{
      date                         = null
      days                         = null
      expired_object_delete_marker = null
    }]
    id = null
    noncurrent_version_expiration = [{
      days = null
    }]
    prefix = null
  }]

  versioning = [{
    enabled = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acl" {
  description = "(optional) - Canned ACL applied on bucket creation"
  type        = string
  default     = null
}

variable "force_destroy" {
  description = "(optional) - Unless true, the bucket will only be destroyed if empty"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - Bucket name"
  type        = string
}

variable "region" {
  description = "(optional) - Bucket region"
  type        = string
  default     = null
}

variable "cors_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allowed_headers = list(string)
      allowed_methods = list(string)
      allowed_origins = list(string)
      max_age_seconds = number
    }
  ))
  default = []
}

variable "lifecycle_rule" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      abort_incomplete_multipart_upload_days = number
      enabled                                = bool
      expiration = set(object(
        {
          date                         = string
          days                         = number
          expired_object_delete_marker = bool
        }
      ))
      id = string
      noncurrent_version_expiration = set(object(
        {
          days = number
        }
      ))
      prefix = string
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
```

[top](#index)

### Resource

```terraform
resource "digitalocean_spaces_bucket" "this" {
  acl           = var.acl
  force_destroy = var.force_destroy
  name          = var.name
  region        = var.region

  dynamic "cors_rule" {
    for_each = var.cors_rule
    content {
      allowed_headers = cors_rule.value["allowed_headers"]
      allowed_methods = cors_rule.value["allowed_methods"]
      allowed_origins = cors_rule.value["allowed_origins"]
      max_age_seconds = cors_rule.value["max_age_seconds"]
    }
  }

  dynamic "lifecycle_rule" {
    for_each = var.lifecycle_rule
    content {
      abort_incomplete_multipart_upload_days = lifecycle_rule.value["abort_incomplete_multipart_upload_days"]
      enabled                                = lifecycle_rule.value["enabled"]
      id                                     = lifecycle_rule.value["id"]
      prefix                                 = lifecycle_rule.value["prefix"]

      dynamic "expiration" {
        for_each = lifecycle_rule.value.expiration
        content {
          date                         = expiration.value["date"]
          days                         = expiration.value["days"]
          expired_object_delete_marker = expiration.value["expired_object_delete_marker"]
        }
      }

      dynamic "noncurrent_version_expiration" {
        for_each = lifecycle_rule.value.noncurrent_version_expiration
        content {
          days = noncurrent_version_expiration.value["days"]
        }
      }

    }
  }

  dynamic "versioning" {
    for_each = var.versioning
    content {
      enabled = versioning.value["enabled"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bucket_domain_name" {
  description = "returns a string"
  value       = digitalocean_spaces_bucket.this.bucket_domain_name
}

output "id" {
  description = "returns a string"
  value       = digitalocean_spaces_bucket.this.id
}

output "urn" {
  description = "returns a string"
  value       = digitalocean_spaces_bucket.this.urn
}

output "this" {
  value = digitalocean_spaces_bucket.this
}
```

[top](#index)