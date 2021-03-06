# aws_pinpoint_app

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
module "aws_pinpoint_app" {
  source = "./modules/aws/r/aws_pinpoint_app"

  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # tags - (optional) is a type of map of string
  tags = {}

  campaign_hook = [{
    lambda_function_name = null
    mode                 = null
    web_url              = null
  }]

  limits = [{
    daily               = null
    maximum_duration    = null
    messages_per_second = null
    total               = null
  }]

  quiet_time = [{
    end   = null
    start = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "campaign_hook" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      lambda_function_name = string
      mode                 = string
      web_url              = string
    }
  ))
  default = []
}

variable "limits" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      daily               = number
      maximum_duration    = number
      messages_per_second = number
      total               = number
    }
  ))
  default = []
}

variable "quiet_time" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      end   = string
      start = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_pinpoint_app" "this" {
  # name - (optional) is a type of string
  name = var.name
  # name_prefix - (optional) is a type of string
  name_prefix = var.name_prefix
  # tags - (optional) is a type of map of string
  tags = var.tags

  dynamic "campaign_hook" {
    for_each = var.campaign_hook
    content {
      # lambda_function_name - (optional) is a type of string
      lambda_function_name = campaign_hook.value["lambda_function_name"]
      # mode - (optional) is a type of string
      mode = campaign_hook.value["mode"]
      # web_url - (optional) is a type of string
      web_url = campaign_hook.value["web_url"]
    }
  }

  dynamic "limits" {
    for_each = var.limits
    content {
      # daily - (optional) is a type of number
      daily = limits.value["daily"]
      # maximum_duration - (optional) is a type of number
      maximum_duration = limits.value["maximum_duration"]
      # messages_per_second - (optional) is a type of number
      messages_per_second = limits.value["messages_per_second"]
      # total - (optional) is a type of number
      total = limits.value["total"]
    }
  }

  dynamic "quiet_time" {
    for_each = var.quiet_time
    content {
      # end - (optional) is a type of string
      end = quiet_time.value["end"]
      # start - (optional) is a type of string
      start = quiet_time.value["start"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "application_id" {
  description = "returns a string"
  value       = aws_pinpoint_app.this.application_id
}

output "arn" {
  description = "returns a string"
  value       = aws_pinpoint_app.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_pinpoint_app.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_pinpoint_app.this.name
}

output "this" {
  value = aws_pinpoint_app.this
}
```

[top](#index)