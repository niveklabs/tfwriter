# aws_imagebuilder_distribution_configuration

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
module "aws_imagebuilder_distribution_configuration" {
  source = "./modules/aws/r/aws_imagebuilder_distribution_configuration"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  distribution = [{
    ami_distribution_configuration = [{
      ami_tags    = {}
      description = null
      kms_key_id  = null
      launch_permission = [{
        user_groups = []
        user_ids    = []
      }]
      name               = null
      target_account_ids = []
    }]
    license_configuration_arns = []
    region                     = null
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

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "distribution" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      ami_distribution_configuration = list(object(
        {
          ami_tags    = map(string)
          description = string
          kms_key_id  = string
          launch_permission = list(object(
            {
              user_groups = set(string)
              user_ids    = set(string)
            }
          ))
          name               = string
          target_account_ids = set(string)
        }
      ))
      license_configuration_arns = set(string)
      region                     = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_imagebuilder_distribution_configuration" "this" {
  # description - (optional) is a type of string
  description = var.description
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "distribution" {
    for_each = var.distribution
    content {
      # license_configuration_arns - (optional) is a type of set of string
      license_configuration_arns = distribution.value["license_configuration_arns"]
      # region - (required) is a type of string
      region = distribution.value["region"]

      dynamic "ami_distribution_configuration" {
        for_each = distribution.value.ami_distribution_configuration
        content {
          # ami_tags - (optional) is a type of map of string
          ami_tags = ami_distribution_configuration.value["ami_tags"]
          # description - (optional) is a type of string
          description = ami_distribution_configuration.value["description"]
          # kms_key_id - (optional) is a type of string
          kms_key_id = ami_distribution_configuration.value["kms_key_id"]
          # name - (optional) is a type of string
          name = ami_distribution_configuration.value["name"]
          # target_account_ids - (optional) is a type of set of string
          target_account_ids = ami_distribution_configuration.value["target_account_ids"]

          dynamic "launch_permission" {
            for_each = ami_distribution_configuration.value.launch_permission
            content {
              # user_groups - (optional) is a type of set of string
              user_groups = launch_permission.value["user_groups"]
              # user_ids - (optional) is a type of set of string
              user_ids = launch_permission.value["user_ids"]
            }
          }

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
  value       = aws_imagebuilder_distribution_configuration.this.arn
}

output "date_created" {
  description = "returns a string"
  value       = aws_imagebuilder_distribution_configuration.this.date_created
}

output "date_updated" {
  description = "returns a string"
  value       = aws_imagebuilder_distribution_configuration.this.date_updated
}

output "id" {
  description = "returns a string"
  value       = aws_imagebuilder_distribution_configuration.this.id
}

output "this" {
  value = aws_imagebuilder_distribution_configuration.this
}
```

[top](#index)