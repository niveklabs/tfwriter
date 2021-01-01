# aws_config_configuration_aggregator
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
```hcl
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
  description = "nested mode: NestingList, min items: 0, max items: 1"
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
  description = "nested mode: NestingList, min items: 0, max items: 1"
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
```hcl
resource "aws_config_configuration_aggregator" "this" {
  name = var.name
  tags = var.tags

  dynamic "account_aggregation_source" {
    for_each = var.account_aggregation_source
    content {
      account_ids = account_aggregation_source.value["account_ids"]
      all_regions = account_aggregation_source.value["all_regions"]
      regions     = account_aggregation_source.value["regions"]
    }
  }

  dynamic "organization_aggregation_source" {
    for_each = var.organization_aggregation_source
    content {
      all_regions = organization_aggregation_source.value["all_regions"]
      regions     = organization_aggregation_source.value["regions"]
      role_arn    = organization_aggregation_source.value["role_arn"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
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
