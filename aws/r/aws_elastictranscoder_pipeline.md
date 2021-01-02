# aws_elastictranscoder_pipeline

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_elastictranscoder_pipeline" {
  source = "./modules/aws/r/aws_elastictranscoder_pipeline"

  # aws_kms_key_arn - (optional) is a type of string
  aws_kms_key_arn = null
  # input_bucket - (required) is a type of string
  input_bucket = null
  # name - (optional) is a type of string
  name = null
  # output_bucket - (optional) is a type of string
  output_bucket = null
  # role - (required) is a type of string
  role = null

  content_config = [{
    bucket        = null
    storage_class = null
  }]

  content_config_permissions = [{
    access       = []
    grantee      = null
    grantee_type = null
  }]

  notifications = [{
    completed   = null
    error       = null
    progressing = null
    warning     = null
  }]

  thumbnail_config = [{
    bucket        = null
    storage_class = null
  }]

  thumbnail_config_permissions = [{
    access       = []
    grantee      = null
    grantee_type = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "aws_kms_key_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "input_bucket" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "output_bucket" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "content_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket        = string
      storage_class = string
    }
  ))
  default = []
}

variable "content_config_permissions" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access       = list(string)
      grantee      = string
      grantee_type = string
    }
  ))
  default = []
}

variable "notifications" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      completed   = string
      error       = string
      progressing = string
      warning     = string
    }
  ))
  default = []
}

variable "thumbnail_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      bucket        = string
      storage_class = string
    }
  ))
  default = []
}

variable "thumbnail_config_permissions" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      access       = list(string)
      grantee      = string
      grantee_type = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_elastictranscoder_pipeline" "this" {
  aws_kms_key_arn = var.aws_kms_key_arn
  input_bucket    = var.input_bucket
  name            = var.name
  output_bucket   = var.output_bucket
  role            = var.role

  dynamic "content_config" {
    for_each = var.content_config
    content {
      bucket        = content_config.value["bucket"]
      storage_class = content_config.value["storage_class"]
    }
  }

  dynamic "content_config_permissions" {
    for_each = var.content_config_permissions
    content {
      access       = content_config_permissions.value["access"]
      grantee      = content_config_permissions.value["grantee"]
      grantee_type = content_config_permissions.value["grantee_type"]
    }
  }

  dynamic "notifications" {
    for_each = var.notifications
    content {
      completed   = notifications.value["completed"]
      error       = notifications.value["error"]
      progressing = notifications.value["progressing"]
      warning     = notifications.value["warning"]
    }
  }

  dynamic "thumbnail_config" {
    for_each = var.thumbnail_config
    content {
      bucket        = thumbnail_config.value["bucket"]
      storage_class = thumbnail_config.value["storage_class"]
    }
  }

  dynamic "thumbnail_config_permissions" {
    for_each = var.thumbnail_config_permissions
    content {
      access       = thumbnail_config_permissions.value["access"]
      grantee      = thumbnail_config_permissions.value["grantee"]
      grantee_type = thumbnail_config_permissions.value["grantee_type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_elastictranscoder_pipeline.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_elastictranscoder_pipeline.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_elastictranscoder_pipeline.this.name
}

output "output_bucket" {
  description = "returns a string"
  value       = aws_elastictranscoder_pipeline.this.output_bucket
}

output "this" {
  value = aws_elastictranscoder_pipeline.this
}
```

[top](#index)