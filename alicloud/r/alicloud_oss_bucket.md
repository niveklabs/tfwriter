# alicloud_oss_bucket

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_oss_bucket" {
  source = "./modules/alicloud/r/alicloud_oss_bucket"

  # acl - (optional) is a type of string
  acl = null
  # bucket - (optional) is a type of string
  bucket = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # logging_isenable - (optional) is a type of bool
  logging_isenable = null
  # policy - (optional) is a type of string
  policy = null
  # redundancy_type - (optional) is a type of string
  redundancy_type = null
  # storage_class - (optional) is a type of string
  storage_class = null
  # tags - (optional) is a type of map of string
  tags = {}

  cors_rule = [{
    allowed_headers = []
    allowed_methods = []
    allowed_origins = []
    expose_headers  = []
    max_age_seconds = null
  }]

  lifecycle_rule = [{
    enabled = null
    expiration = [{
      date = null
      days = null
    }]
    id     = null
    prefix = null
    transitions = [{
      created_before_date = null
      days                = null
      storage_class       = null
    }]
  }]

  logging = [{
    target_bucket = null
    target_prefix = null
  }]

  referer_config = [{
    allow_empty = null
    referers    = []
  }]

  server_side_encryption_rule = [{
    kms_master_key_id = null
    sse_algorithm     = null
  }]

  versioning = [{
    status = null
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "bucket" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "logging_isenable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "redundancy_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "storage_class" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "cors_rule" {
  description = "nested block: NestingList, min items: 0, max items: 10"
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

variable "lifecycle_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1000"
  type = set(object(
    {
      enabled = bool
      expiration = set(object(
        {
          date = string
          days = number
        }
      ))
      id     = string
      prefix = string
      transitions = set(object(
        {
          created_before_date = string
          days                = number
          storage_class       = string
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
      target_bucket = string
      target_prefix = string
    }
  ))
  default = []
}

variable "referer_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_empty = bool
      referers    = list(string)
    }
  ))
  default = []
}

variable "server_side_encryption_rule" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      kms_master_key_id = string
      sse_algorithm     = string
    }
  ))
  default = []
}

variable "versioning" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      status = string
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
resource "alicloud_oss_bucket" "this" {
  acl              = var.acl
  bucket           = var.bucket
  force_destroy    = var.force_destroy
  logging_isenable = var.logging_isenable
  policy           = var.policy
  redundancy_type  = var.redundancy_type
  storage_class    = var.storage_class
  tags             = var.tags

  dynamic "cors_rule" {
    for_each = var.cors_rule
    content {
      allowed_headers = cors_rule.value["allowed_headers"]
      allowed_methods = cors_rule.value["allowed_methods"]
      allowed_origins = cors_rule.value["allowed_origins"]
      expose_headers  = cors_rule.value["expose_headers"]
      max_age_seconds = cors_rule.value["max_age_seconds"]
    }
  }

  dynamic "lifecycle_rule" {
    for_each = var.lifecycle_rule
    content {
      enabled = lifecycle_rule.value["enabled"]
      id      = lifecycle_rule.value["id"]
      prefix  = lifecycle_rule.value["prefix"]

      dynamic "expiration" {
        for_each = lifecycle_rule.value.expiration
        content {
          date = expiration.value["date"]
          days = expiration.value["days"]
        }
      }

      dynamic "transitions" {
        for_each = lifecycle_rule.value.transitions
        content {
          created_before_date = transitions.value["created_before_date"]
          days                = transitions.value["days"]
          storage_class       = transitions.value["storage_class"]
        }
      }

    }
  }

  dynamic "logging" {
    for_each = var.logging
    content {
      target_bucket = logging.value["target_bucket"]
      target_prefix = logging.value["target_prefix"]
    }
  }

  dynamic "referer_config" {
    for_each = var.referer_config
    content {
      allow_empty = referer_config.value["allow_empty"]
      referers    = referer_config.value["referers"]
    }
  }

  dynamic "server_side_encryption_rule" {
    for_each = var.server_side_encryption_rule
    content {
      kms_master_key_id = server_side_encryption_rule.value["kms_master_key_id"]
      sse_algorithm     = server_side_encryption_rule.value["sse_algorithm"]
    }
  }

  dynamic "versioning" {
    for_each = var.versioning
    content {
      status = versioning.value["status"]
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
output "creation_date" {
  description = "returns a string"
  value       = alicloud_oss_bucket.this.creation_date
}

output "extranet_endpoint" {
  description = "returns a string"
  value       = alicloud_oss_bucket.this.extranet_endpoint
}

output "id" {
  description = "returns a string"
  value       = alicloud_oss_bucket.this.id
}

output "intranet_endpoint" {
  description = "returns a string"
  value       = alicloud_oss_bucket.this.intranet_endpoint
}

output "location" {
  description = "returns a string"
  value       = alicloud_oss_bucket.this.location
}

output "owner" {
  description = "returns a string"
  value       = alicloud_oss_bucket.this.owner
}

output "this" {
  value = alicloud_oss_bucket.this
}
```

[top](#index)