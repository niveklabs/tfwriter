# aws_imagebuilder_infrastructure_configuration

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
module "aws_imagebuilder_infrastructure_configuration" {
  source = "./modules/aws/r/aws_imagebuilder_infrastructure_configuration"

  # description - (optional) is a type of string
  description = null
  # instance_profile_name - (required) is a type of string
  instance_profile_name = null
  # instance_types - (optional) is a type of set of string
  instance_types = []
  # key_pair - (optional) is a type of string
  key_pair = null
  # name - (required) is a type of string
  name = null
  # resource_tags - (optional) is a type of map of string
  resource_tags = {}
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = []
  # sns_topic_arn - (optional) is a type of string
  sns_topic_arn = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # terminate_instance_on_failure - (optional) is a type of bool
  terminate_instance_on_failure = null

  logging = [{
    s3_logs = [{
      s3_bucket_name = null
      s3_key_prefix  = null
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

variable "instance_profile_name" {
  description = "(required)"
  type        = string
}

variable "instance_types" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "key_pair" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "security_group_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "sns_topic_arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "terminate_instance_on_failure" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "logging" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      s3_logs = list(object(
        {
          s3_bucket_name = string
          s3_key_prefix  = string
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
resource "aws_imagebuilder_infrastructure_configuration" "this" {
  # description - (optional) is a type of string
  description = var.description
  # instance_profile_name - (required) is a type of string
  instance_profile_name = var.instance_profile_name
  # instance_types - (optional) is a type of set of string
  instance_types = var.instance_types
  # key_pair - (optional) is a type of string
  key_pair = var.key_pair
  # name - (required) is a type of string
  name = var.name
  # resource_tags - (optional) is a type of map of string
  resource_tags = var.resource_tags
  # security_group_ids - (optional) is a type of set of string
  security_group_ids = var.security_group_ids
  # sns_topic_arn - (optional) is a type of string
  sns_topic_arn = var.sns_topic_arn
  # subnet_id - (optional) is a type of string
  subnet_id = var.subnet_id
  # tags - (optional) is a type of map of string
  tags = var.tags
  # terminate_instance_on_failure - (optional) is a type of bool
  terminate_instance_on_failure = var.terminate_instance_on_failure

  dynamic "logging" {
    for_each = var.logging
    content {

      dynamic "s3_logs" {
        for_each = logging.value.s3_logs
        content {
          # s3_bucket_name - (required) is a type of string
          s3_bucket_name = s3_logs.value["s3_bucket_name"]
          # s3_key_prefix - (optional) is a type of string
          s3_key_prefix = s3_logs.value["s3_key_prefix"]
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
  value       = aws_imagebuilder_infrastructure_configuration.this.arn
}

output "date_created" {
  description = "returns a string"
  value       = aws_imagebuilder_infrastructure_configuration.this.date_created
}

output "date_updated" {
  description = "returns a string"
  value       = aws_imagebuilder_infrastructure_configuration.this.date_updated
}

output "id" {
  description = "returns a string"
  value       = aws_imagebuilder_infrastructure_configuration.this.id
}

output "this" {
  value = aws_imagebuilder_infrastructure_configuration.this
}
```

[top](#index)