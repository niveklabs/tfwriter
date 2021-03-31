# aws_api_gateway_usage_plan

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_api_gateway_usage_plan" {
  source = "./modules/aws/r/aws_api_gateway_usage_plan"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # product_code - (optional) is a type of string
  product_code = null
  # tags - (optional) is a type of map of string
  tags = {}

  api_stages = [{
    api_id = null
    stage  = null
  }]

  quota_settings = [{
    limit  = null
    offset = null
    period = null
  }]

  throttle_settings = [{
    burst_limit = null
    rate_limit  = null
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

variable "product_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "api_stages" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      api_id = string
      stage  = string
    }
  ))
  default = []
}

variable "quota_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      limit  = number
      offset = number
      period = string
    }
  ))
  default = []
}

variable "throttle_settings" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      burst_limit = number
      rate_limit  = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_usage_plan" "this" {
  description  = var.description
  name         = var.name
  product_code = var.product_code
  tags         = var.tags

  dynamic "api_stages" {
    for_each = var.api_stages
    content {
      api_id = api_stages.value["api_id"]
      stage  = api_stages.value["stage"]
    }
  }

  dynamic "quota_settings" {
    for_each = var.quota_settings
    content {
      limit  = quota_settings.value["limit"]
      offset = quota_settings.value["offset"]
      period = quota_settings.value["period"]
    }
  }

  dynamic "throttle_settings" {
    for_each = var.throttle_settings
    content {
      burst_limit = throttle_settings.value["burst_limit"]
      rate_limit  = throttle_settings.value["rate_limit"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_api_gateway_usage_plan.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_api_gateway_usage_plan.this.id
}

output "this" {
  value = aws_api_gateway_usage_plan.this
}
```

[top](#index)