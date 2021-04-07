# aws_s3_bucket

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_s3_bucket" {
  source = "./modules/aws/r/aws_s3_bucket"

  # acceleration_status - (optional) is a type of string
  acceleration_status = null
  # acl - (optional) is a type of string
  acl = null
  # arn - (optional) is a type of string
  arn = null
  # bucket - (optional) is a type of string
  bucket = null
  # bucket_prefix - (optional) is a type of string
  bucket_prefix = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # hosted_zone_id - (optional) is a type of string
  hosted_zone_id = null
  # policy - (optional) is a type of string
  policy = null
  # request_payer - (optional) is a type of string
  request_payer = null
  # tags - (optional) is a type of map of string
  tags = {}
  # website_domain - (optional) is a type of string
  website_domain = null
  # website_endpoint - (optional) is a type of string
  website_endpoint = null

  cors_rule = [{
    allowed_headers = []
    allowed_methods = []
    allowed_origins = []
    expose_headers  = []
    max_age_seconds = null
  }]

  grant = [{
    id          = null
    permissions = []
    type        = null
    uri         = null
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
    noncurrent_version_transition = [{
      days          = null
      storage_class = null
    }]
    prefix = null
    tags   = {}
    transition = [{
      date          = null
      days          = null
      storage_class = null
    }]
  }]

  logging = [{
    target_bucket = null
    target_prefix = null
  }]

  object_lock_configuration = [{
    object_lock_enabled = null
    rule = [{
      default_retention = [{
        days  = null
        mode  = null
        years = null
      }]
    }]
  }]

  replication_configuration = [{
    role = null
    rules = [{
      destination = [{
        access_control_translation = [{
          owner = null
        }]
        account_id         = null
        bucket             = null
        replica_kms_key_id = null
        storage_class      = null
      }]
      filter = [{
        prefix = null
        tags   = {}
      }]
      id       = null
      prefix   = null
      priority = null
      source_selection_criteria = [{
        sse_kms_encrypted_objects = [{
          enabled = null
        }]
      }]
      status = null
    }]
  }]

  server_side_encryption_configuration = [{
    rule = [{
      apply_server_side_encryption_by_default = [{
        kms_master_key_id = null
        sse_algorithm     = null
      }]
    }]
  }]

  versioning = [{
    enabled    = null
    mfa_delete = null
  }]

  website = [{
    error_document           = null
    index_document           = null
    redirect_all_requests_to = null
    routing_rules            = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "acceleration_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "acl" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bucket" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "bucket_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hosted_zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "policy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "request_payer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "website_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "website_endpoint" {
  description = "(optional)"
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
      expose_headers  = list(string)
      max_age_seconds = number
    }
  ))
  default = []
}

variable "grant" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id          = string
      permissions = set(string)
      type        = string
      uri         = string
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
      expiration = list(object(
        {
          date                         = string
          days                         = number
          expired_object_delete_marker = bool
        }
      ))
      id = string
      noncurrent_version_expiration = list(object(
        {
          days = number
        }
      ))
      noncurrent_version_transition = set(object(
        {
          days          = number
          storage_class = string
        }
      ))
      prefix = string
      tags   = map(string)
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

variable "logging" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      target_bucket = string
      target_prefix = string
    }
  ))
  default = []
}

variable "object_lock_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      object_lock_enabled = string
      rule = list(object(
        {
          default_retention = list(object(
            {
              days  = number
              mode  = string
              years = number
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "replication_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      role = string
      rules = set(object(
        {
          destination = list(object(
            {
              access_control_translation = list(object(
                {
                  owner = string
                }
              ))
              account_id         = string
              bucket             = string
              replica_kms_key_id = string
              storage_class      = string
            }
          ))
          filter = list(object(
            {
              prefix = string
              tags   = map(string)
            }
          ))
          id       = string
          prefix   = string
          priority = number
          source_selection_criteria = list(object(
            {
              sse_kms_encrypted_objects = list(object(
                {
                  enabled = bool
                }
              ))
            }
          ))
          status = string
        }
      ))
    }
  ))
  default = []
}

variable "server_side_encryption_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      rule = list(object(
        {
          apply_server_side_encryption_by_default = list(object(
            {
              kms_master_key_id = string
              sse_algorithm     = string
            }
          ))
        }
      ))
    }
  ))
  default = []
}

variable "versioning" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled    = bool
      mfa_delete = bool
    }
  ))
  default = []
}

variable "website" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      error_document           = string
      index_document           = string
      redirect_all_requests_to = string
      routing_rules            = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_s3_bucket" "this" {
  # acceleration_status - (optional) is a type of string
  acceleration_status = var.acceleration_status
  # acl - (optional) is a type of string
  acl = var.acl
  # arn - (optional) is a type of string
  arn = var.arn
  # bucket - (optional) is a type of string
  bucket = var.bucket
  # bucket_prefix - (optional) is a type of string
  bucket_prefix = var.bucket_prefix
  # force_destroy - (optional) is a type of bool
  force_destroy = var.force_destroy
  # hosted_zone_id - (optional) is a type of string
  hosted_zone_id = var.hosted_zone_id
  # policy - (optional) is a type of string
  policy = var.policy
  # request_payer - (optional) is a type of string
  request_payer = var.request_payer
  # tags - (optional) is a type of map of string
  tags = var.tags
  # website_domain - (optional) is a type of string
  website_domain = var.website_domain
  # website_endpoint - (optional) is a type of string
  website_endpoint = var.website_endpoint

  dynamic "cors_rule" {
    for_each = var.cors_rule
    content {
      # allowed_headers - (optional) is a type of list of string
      allowed_headers = cors_rule.value["allowed_headers"]
      # allowed_methods - (required) is a type of list of string
      allowed_methods = cors_rule.value["allowed_methods"]
      # allowed_origins - (required) is a type of list of string
      allowed_origins = cors_rule.value["allowed_origins"]
      # expose_headers - (optional) is a type of list of string
      expose_headers = cors_rule.value["expose_headers"]
      # max_age_seconds - (optional) is a type of number
      max_age_seconds = cors_rule.value["max_age_seconds"]
    }
  }

  dynamic "grant" {
    for_each = var.grant
    content {
      # id - (optional) is a type of string
      id = grant.value["id"]
      # permissions - (required) is a type of set of string
      permissions = grant.value["permissions"]
      # type - (required) is a type of string
      type = grant.value["type"]
      # uri - (optional) is a type of string
      uri = grant.value["uri"]
    }
  }

  dynamic "lifecycle_rule" {
    for_each = var.lifecycle_rule
    content {
      # abort_incomplete_multipart_upload_days - (optional) is a type of number
      abort_incomplete_multipart_upload_days = lifecycle_rule.value["abort_incomplete_multipart_upload_days"]
      # enabled - (required) is a type of bool
      enabled = lifecycle_rule.value["enabled"]
      # id - (optional) is a type of string
      id = lifecycle_rule.value["id"]
      # prefix - (optional) is a type of string
      prefix = lifecycle_rule.value["prefix"]
      # tags - (optional) is a type of map of string
      tags = lifecycle_rule.value["tags"]

      dynamic "expiration" {
        for_each = lifecycle_rule.value.expiration
        content {
          # date - (optional) is a type of string
          date = expiration.value["date"]
          # days - (optional) is a type of number
          days = expiration.value["days"]
          # expired_object_delete_marker - (optional) is a type of bool
          expired_object_delete_marker = expiration.value["expired_object_delete_marker"]
        }
      }

      dynamic "noncurrent_version_expiration" {
        for_each = lifecycle_rule.value.noncurrent_version_expiration
        content {
          # days - (optional) is a type of number
          days = noncurrent_version_expiration.value["days"]
        }
      }

      dynamic "noncurrent_version_transition" {
        for_each = lifecycle_rule.value.noncurrent_version_transition
        content {
          # days - (optional) is a type of number
          days = noncurrent_version_transition.value["days"]
          # storage_class - (required) is a type of string
          storage_class = noncurrent_version_transition.value["storage_class"]
        }
      }

      dynamic "transition" {
        for_each = lifecycle_rule.value.transition
        content {
          # date - (optional) is a type of string
          date = transition.value["date"]
          # days - (optional) is a type of number
          days = transition.value["days"]
          # storage_class - (required) is a type of string
          storage_class = transition.value["storage_class"]
        }
      }

    }
  }

  dynamic "logging" {
    for_each = var.logging
    content {
      # target_bucket - (required) is a type of string
      target_bucket = logging.value["target_bucket"]
      # target_prefix - (optional) is a type of string
      target_prefix = logging.value["target_prefix"]
    }
  }

  dynamic "object_lock_configuration" {
    for_each = var.object_lock_configuration
    content {
      # object_lock_enabled - (required) is a type of string
      object_lock_enabled = object_lock_configuration.value["object_lock_enabled"]

      dynamic "rule" {
        for_each = object_lock_configuration.value.rule
        content {

          dynamic "default_retention" {
            for_each = rule.value.default_retention
            content {
              # days - (optional) is a type of number
              days = default_retention.value["days"]
              # mode - (required) is a type of string
              mode = default_retention.value["mode"]
              # years - (optional) is a type of number
              years = default_retention.value["years"]
            }
          }

        }
      }

    }
  }

  dynamic "replication_configuration" {
    for_each = var.replication_configuration
    content {
      # role - (required) is a type of string
      role = replication_configuration.value["role"]

      dynamic "rules" {
        for_each = replication_configuration.value.rules
        content {
          # id - (optional) is a type of string
          id = rules.value["id"]
          # prefix - (optional) is a type of string
          prefix = rules.value["prefix"]
          # priority - (optional) is a type of number
          priority = rules.value["priority"]
          # status - (required) is a type of string
          status = rules.value["status"]

          dynamic "destination" {
            for_each = rules.value.destination
            content {
              # account_id - (optional) is a type of string
              account_id = destination.value["account_id"]
              # bucket - (required) is a type of string
              bucket = destination.value["bucket"]
              # replica_kms_key_id - (optional) is a type of string
              replica_kms_key_id = destination.value["replica_kms_key_id"]
              # storage_class - (optional) is a type of string
              storage_class = destination.value["storage_class"]

              dynamic "access_control_translation" {
                for_each = destination.value.access_control_translation
                content {
                  # owner - (required) is a type of string
                  owner = access_control_translation.value["owner"]
                }
              }

            }
          }

          dynamic "filter" {
            for_each = rules.value.filter
            content {
              # prefix - (optional) is a type of string
              prefix = filter.value["prefix"]
              # tags - (optional) is a type of map of string
              tags = filter.value["tags"]
            }
          }

          dynamic "source_selection_criteria" {
            for_each = rules.value.source_selection_criteria
            content {

              dynamic "sse_kms_encrypted_objects" {
                for_each = source_selection_criteria.value.sse_kms_encrypted_objects
                content {
                  # enabled - (required) is a type of bool
                  enabled = sse_kms_encrypted_objects.value["enabled"]
                }
              }

            }
          }

        }
      }

    }
  }

  dynamic "server_side_encryption_configuration" {
    for_each = var.server_side_encryption_configuration
    content {

      dynamic "rule" {
        for_each = server_side_encryption_configuration.value.rule
        content {

          dynamic "apply_server_side_encryption_by_default" {
            for_each = rule.value.apply_server_side_encryption_by_default
            content {
              # kms_master_key_id - (optional) is a type of string
              kms_master_key_id = apply_server_side_encryption_by_default.value["kms_master_key_id"]
              # sse_algorithm - (required) is a type of string
              sse_algorithm = apply_server_side_encryption_by_default.value["sse_algorithm"]
            }
          }

        }
      }

    }
  }

  dynamic "versioning" {
    for_each = var.versioning
    content {
      # enabled - (optional) is a type of bool
      enabled = versioning.value["enabled"]
      # mfa_delete - (optional) is a type of bool
      mfa_delete = versioning.value["mfa_delete"]
    }
  }

  dynamic "website" {
    for_each = var.website
    content {
      # error_document - (optional) is a type of string
      error_document = website.value["error_document"]
      # index_document - (optional) is a type of string
      index_document = website.value["index_document"]
      # redirect_all_requests_to - (optional) is a type of string
      redirect_all_requests_to = website.value["redirect_all_requests_to"]
      # routing_rules - (optional) is a type of string
      routing_rules = website.value["routing_rules"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "acceleration_status" {
  description = "returns a string"
  value       = aws_s3_bucket.this.acceleration_status
}

output "arn" {
  description = "returns a string"
  value       = aws_s3_bucket.this.arn
}

output "bucket" {
  description = "returns a string"
  value       = aws_s3_bucket.this.bucket
}

output "bucket_domain_name" {
  description = "returns a string"
  value       = aws_s3_bucket.this.bucket_domain_name
}

output "bucket_regional_domain_name" {
  description = "returns a string"
  value       = aws_s3_bucket.this.bucket_regional_domain_name
}

output "hosted_zone_id" {
  description = "returns a string"
  value       = aws_s3_bucket.this.hosted_zone_id
}

output "id" {
  description = "returns a string"
  value       = aws_s3_bucket.this.id
}

output "region" {
  description = "returns a string"
  value       = aws_s3_bucket.this.region
}

output "request_payer" {
  description = "returns a string"
  value       = aws_s3_bucket.this.request_payer
}

output "website_domain" {
  description = "returns a string"
  value       = aws_s3_bucket.this.website_domain
}

output "website_endpoint" {
  description = "returns a string"
  value       = aws_s3_bucket.this.website_endpoint
}

output "this" {
  value = aws_s3_bucket.this
}
```

[top](#index)