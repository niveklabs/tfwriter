# aws_pinpoint_app
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
```hcl
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
  description = "nested mode: NestingList, min items: 0, max items: 1"
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
  description = "nested mode: NestingList, min items: 0, max items: 1"
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
  description = "nested mode: NestingList, min items: 0, max items: 1"
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
```hcl
resource "aws_pinpoint_app" "this" {
  name        = var.name
  name_prefix = var.name_prefix
  tags        = var.tags

  dynamic "campaign_hook" {
    for_each = var.campaign_hook
    content {
      lambda_function_name = campaign_hook.value["lambda_function_name"]
      mode                 = campaign_hook.value["mode"]
      web_url              = campaign_hook.value["web_url"]
    }
  }

  dynamic "limits" {
    for_each = var.limits
    content {
      daily               = limits.value["daily"]
      maximum_duration    = limits.value["maximum_duration"]
      messages_per_second = limits.value["messages_per_second"]
      total               = limits.value["total"]
    }
  }

  dynamic "quiet_time" {
    for_each = var.quiet_time
    content {
      end   = quiet_time.value["end"]
      start = quiet_time.value["start"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
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
