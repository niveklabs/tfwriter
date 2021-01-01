# aws_imagebuilder_distribution_configuration

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```hcl
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

```hcl
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
  description = "nested mode: NestingSet, min items: 1, max items: 0"
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

```hcl
resource "aws_imagebuilder_distribution_configuration" "this" {
  description = var.description
  name        = var.name
  tags        = var.tags

  dynamic "distribution" {
    for_each = var.distribution
    content {
      license_configuration_arns = distribution.value["license_configuration_arns"]
      region                     = distribution.value["region"]

      dynamic "ami_distribution_configuration" {
        for_each = distribution.value.ami_distribution_configuration
        content {
          ami_tags           = ami_distribution_configuration.value["ami_tags"]
          description        = ami_distribution_configuration.value["description"]
          kms_key_id         = ami_distribution_configuration.value["kms_key_id"]
          name               = ami_distribution_configuration.value["name"]
          target_account_ids = ami_distribution_configuration.value["target_account_ids"]

          dynamic "launch_permission" {
            for_each = ami_distribution_configuration.value.launch_permission
            content {
              user_groups = launch_permission.value["user_groups"]
              user_ids    = launch_permission.value["user_ids"]
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

```hcl
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