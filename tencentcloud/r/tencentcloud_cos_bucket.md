# tencentcloud_cos_bucket

[back](../tencentcloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    tencentcloud = ">= 1.56.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "tencentcloud_cos_bucket" {
  source = "./modules/tencentcloud/r/tencentcloud_cos_bucket"

  # acl - (optional) is a type of string
  acl = null
  # bucket - (required) is a type of string
  bucket = null
  # encryption_algorithm - (optional) is a type of string
  encryption_algorithm = null
  # log_enable - (optional) is a type of bool
  log_enable = null
  # log_prefix - (optional) is a type of string
  log_prefix = null
  # log_target_bucket - (optional) is a type of string
  log_target_bucket = null
  # tags - (optional) is a type of map of string
  tags = {}
  # versioning_enable - (optional) is a type of bool
  versioning_enable = null

  cors_rules = [{
    allowed_headers = []
    allowed_methods = []
    allowed_origins = []
    expose_headers  = []
    max_age_seconds = null
  }]

  lifecycle_rules = [{
    expiration = [{
      date = null
      days = null
    }]
    filter_prefix = null
    transition = [{
      date          = null
      days          = null
      storage_class = null
    }]
  }]

  website = [{
    error_document = null
    index_document = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acl" {
  description = "(optional) - The canned ACL to apply. Valid values: private, public-read, and public-read-write. Defaults to private."
  type        = string
  default     = null
}

variable "bucket" {
  description = "(required) - The name of a bucket to be created. Bucket format should be [custom name]-[appid], for example `mycos-1258798060`."
  type        = string
}

variable "encryption_algorithm" {
  description = "(optional) - The server-side encryption algorithm to use. Valid value is `AES256`."
  type        = string
  default     = null
}

variable "log_enable" {
  description = "(optional) - Indicate the access log of this bucket to be saved or not. Default is `false`. If set `true`, the access log will be saved with `log_target_bucket`. To enable log, the full access of log service must be granted. [Full Access Role Policy](https://intl.cloud.tencent.com/document/product/436/16920)."
  type        = bool
  default     = null
}

variable "log_prefix" {
  description = "(optional) - The prefix log name which saves the access log of this bucket per 5 minutes. Eg. `MyLogPrefix/`. The log access file format is `log_target_bucket`/`log_prefix`{YYYY}/{MM}/{DD}/{time}_{random}_{index}.gz. Only valid when `log_enable` is `true`."
  type        = string
  default     = null
}

variable "log_target_bucket" {
  description = "(optional) - The target bucket name which saves the access log of this bucket per 5 minutes. The log access file format is `log_target_bucket`/`log_prefix`{YYYY}/{MM}/{DD}/{time}_{random}_{index}.gz. Only valid when `log_enable` is `true`. User must have full access on this bucket."
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The tags of a bucket."
  type        = map(string)
  default     = null
}

variable "versioning_enable" {
  description = "(optional) - Enable bucket versioning."
  type        = bool
  default     = null
}

variable "cors_rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      allowed_headers = list(string)
      allowed_methods = list(string)
      allowed_origins = list(string)
      expose_headers  = list(string)
      max_age_seconds = number
    }
  ))
  default = []
}

variable "lifecycle_rules" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      expiration = set(object(
        {
          date = string
          days = number
        }
      ))
      filter_prefix = string
      transition = set(object(
        {
          date          = string
          days          = number
          storage_class = string
        }
      ))
    }
  ))
  default = []
}

variable "website" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      error_document = string
      index_document = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "tencentcloud_cos_bucket" "this" {
  acl                  = var.acl
  bucket               = var.bucket
  encryption_algorithm = var.encryption_algorithm
  log_enable           = var.log_enable
  log_prefix           = var.log_prefix
  log_target_bucket    = var.log_target_bucket
  tags                 = var.tags
  versioning_enable    = var.versioning_enable

  dynamic "cors_rules" {
    for_each = var.cors_rules
    content {
      allowed_headers = cors_rules.value["allowed_headers"]
      allowed_methods = cors_rules.value["allowed_methods"]
      allowed_origins = cors_rules.value["allowed_origins"]
      expose_headers  = cors_rules.value["expose_headers"]
      max_age_seconds = cors_rules.value["max_age_seconds"]
    }
  }

  dynamic "lifecycle_rules" {
    for_each = var.lifecycle_rules
    content {
      filter_prefix = lifecycle_rules.value["filter_prefix"]

      dynamic "expiration" {
        for_each = lifecycle_rules.value.expiration
        content {
          date = expiration.value["date"]
          days = expiration.value["days"]
        }
      }

      dynamic "transition" {
        for_each = lifecycle_rules.value.transition
        content {
          date          = transition.value["date"]
          days          = transition.value["days"]
          storage_class = transition.value["storage_class"]
        }
      }

    }
  }

  dynamic "website" {
    for_each = var.website
    content {
      error_document = website.value["error_document"]
      index_document = website.value["index_document"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cos_bucket_url" {
  description = "returns a string"
  value       = tencentcloud_cos_bucket.this.cos_bucket_url
}

output "id" {
  description = "returns a string"
  value       = tencentcloud_cos_bucket.this.id
}

output "log_prefix" {
  description = "returns a string"
  value       = tencentcloud_cos_bucket.this.log_prefix
}

output "log_target_bucket" {
  description = "returns a string"
  value       = tencentcloud_cos_bucket.this.log_target_bucket
}

output "this" {
  value = tencentcloud_cos_bucket.this
}
```

[top](#index)