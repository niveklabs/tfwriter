# aws_sagemaker_feature_group

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
module "aws_sagemaker_feature_group" {
  source = "./modules/aws/r/aws_sagemaker_feature_group"

  # description - (optional) is a type of string
  description = null
  # event_time_feature_name - (required) is a type of string
  event_time_feature_name = null
  # feature_group_name - (required) is a type of string
  feature_group_name = null
  # record_identifier_feature_name - (required) is a type of string
  record_identifier_feature_name = null
  # role_arn - (required) is a type of string
  role_arn = null
  # tags - (optional) is a type of map of string
  tags = {}

  feature_definition = [{
    feature_name = null
    feature_type = null
  }]

  offline_store_config = [{
    data_catalog_config = [{
      catalog    = null
      database   = null
      table_name = null
    }]
    disable_glue_table_creation = null
    s3_storage_config = [{
      kms_key_id = null
      s3_uri     = null
    }]
  }]

  online_store_config = [{
    enable_online_store = null
    security_config = [{
      kms_key_id = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "event_time_feature_name" {
  description = "(required)"
  type        = string
}

variable "feature_group_name" {
  description = "(required)"
  type        = string
}

variable "record_identifier_feature_name" {
  description = "(required)"
  type        = string
}

variable "role_arn" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "feature_definition" {
  description = "nested block: NestingList, min items: 1, max items: 2500"
  type = set(object(
    {
      feature_name = string
      feature_type = string
    }
  ))
}

variable "offline_store_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      data_catalog_config = list(object(
        {
          catalog    = string
          database   = string
          table_name = string
        }
      ))
      disable_glue_table_creation = bool
      s3_storage_config = list(object(
        {
          kms_key_id = string
          s3_uri     = string
        }
      ))
    }
  ))
  default = []
}

variable "online_store_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enable_online_store = bool
      security_config = list(object(
        {
          kms_key_id = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_sagemaker_feature_group" "this" {
  description                    = var.description
  event_time_feature_name        = var.event_time_feature_name
  feature_group_name             = var.feature_group_name
  record_identifier_feature_name = var.record_identifier_feature_name
  role_arn                       = var.role_arn
  tags                           = var.tags

  dynamic "feature_definition" {
    for_each = var.feature_definition
    content {
      feature_name = feature_definition.value["feature_name"]
      feature_type = feature_definition.value["feature_type"]
    }
  }

  dynamic "offline_store_config" {
    for_each = var.offline_store_config
    content {
      disable_glue_table_creation = offline_store_config.value["disable_glue_table_creation"]

      dynamic "data_catalog_config" {
        for_each = offline_store_config.value.data_catalog_config
        content {
          catalog    = data_catalog_config.value["catalog"]
          database   = data_catalog_config.value["database"]
          table_name = data_catalog_config.value["table_name"]
        }
      }

      dynamic "s3_storage_config" {
        for_each = offline_store_config.value.s3_storage_config
        content {
          kms_key_id = s3_storage_config.value["kms_key_id"]
          s3_uri     = s3_storage_config.value["s3_uri"]
        }
      }

    }
  }

  dynamic "online_store_config" {
    for_each = var.online_store_config
    content {
      enable_online_store = online_store_config.value["enable_online_store"]

      dynamic "security_config" {
        for_each = online_store_config.value.security_config
        content {
          kms_key_id = security_config.value["kms_key_id"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sagemaker_feature_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_feature_group.this.id
}

output "this" {
  value = aws_sagemaker_feature_group.this
}
```

[top](#index)