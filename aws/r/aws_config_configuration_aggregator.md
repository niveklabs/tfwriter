# aws_config_configuration_aggregator

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
module "aws_config_configuration_aggregator" {
  source = "./modules/aws/r/aws_config_configuration_aggregator"

  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  account_aggregation_source = [{
    account_ids = []
    all_regions = null
    regions     = []
  }]

  organization_aggregation_source = [{
    all_regions = null
    regions     = []
    role_arn    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "account_aggregation_source" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account_ids = list(string)
      all_regions = bool
      regions     = list(string)
    }
  ))
  default = []
}

variable "organization_aggregation_source" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      all_regions = bool
      regions     = list(string)
      role_arn    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_config_configuration_aggregator" "this" {
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "account_aggregation_source" {
    for_each = var.account_aggregation_source
    content {
      # account_ids - (required) is a type of list of string
      account_ids = account_aggregation_source.value["account_ids"]
      # all_regions - (optional) is a type of bool
      all_regions = account_aggregation_source.value["all_regions"]
      # regions - (optional) is a type of list of string
      regions = account_aggregation_source.value["regions"]
    }
  }

  dynamic "organization_aggregation_source" {
    for_each = var.organization_aggregation_source
    content {
      # all_regions - (optional) is a type of bool
      all_regions = organization_aggregation_source.value["all_regions"]
      # regions - (optional) is a type of list of string
      regions = organization_aggregation_source.value["regions"]
      # role_arn - (required) is a type of string
      role_arn = organization_aggregation_source.value["role_arn"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_config_configuration_aggregator.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_config_configuration_aggregator.this.id
}

output "this" {
  value = aws_config_configuration_aggregator.this
}
```

[top](#index)