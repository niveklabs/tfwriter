# aws_apigatewayv2_stage
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
module "aws_apigatewayv2_stage" {
  source = "./modules/aws/r/aws_apigatewayv2_stage"

  # api_id - (required) is a type of string
  api_id = null
  # auto_deploy - (optional) is a type of bool
  auto_deploy = null
  # client_certificate_id - (optional) is a type of string
  client_certificate_id = null
  # deployment_id - (optional) is a type of string
  deployment_id = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # stage_variables - (optional) is a type of map of string
  stage_variables = {}
  # tags - (optional) is a type of map of string
  tags = {}

  access_log_settings = [{
    destination_arn = null
    format          = null
  }]

  default_route_settings = [{
    data_trace_enabled       = null
    detailed_metrics_enabled = null
    logging_level            = null
    throttling_burst_limit   = null
    throttling_rate_limit    = null
  }]

  route_settings = [{
    data_trace_enabled       = null
    detailed_metrics_enabled = null
    logging_level            = null
    route_key                = null
    throttling_burst_limit   = null
    throttling_rate_limit    = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "auto_deploy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "client_certificate_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deployment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "stage_variables" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "access_log_settings" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      destination_arn = string
      format          = string
    }
  ))
  default = []
}

variable "default_route_settings" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      data_trace_enabled       = bool
      detailed_metrics_enabled = bool
      logging_level            = string
      throttling_burst_limit   = number
      throttling_rate_limit    = number
    }
  ))
  default = []
}

variable "route_settings" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      data_trace_enabled       = bool
      detailed_metrics_enabled = bool
      logging_level            = string
      route_key                = string
      throttling_burst_limit   = number
      throttling_rate_limit    = number
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_apigatewayv2_stage" "this" {
  api_id                = var.api_id
  auto_deploy           = var.auto_deploy
  client_certificate_id = var.client_certificate_id
  deployment_id         = var.deployment_id
  description           = var.description
  name                  = var.name
  stage_variables       = var.stage_variables
  tags                  = var.tags

  dynamic "access_log_settings" {
    for_each = var.access_log_settings
    content {
      destination_arn = access_log_settings.value["destination_arn"]
      format          = access_log_settings.value["format"]
    }
  }

  dynamic "default_route_settings" {
    for_each = var.default_route_settings
    content {
      data_trace_enabled       = default_route_settings.value["data_trace_enabled"]
      detailed_metrics_enabled = default_route_settings.value["detailed_metrics_enabled"]
      logging_level            = default_route_settings.value["logging_level"]
      throttling_burst_limit   = default_route_settings.value["throttling_burst_limit"]
      throttling_rate_limit    = default_route_settings.value["throttling_rate_limit"]
    }
  }

  dynamic "route_settings" {
    for_each = var.route_settings
    content {
      data_trace_enabled       = route_settings.value["data_trace_enabled"]
      detailed_metrics_enabled = route_settings.value["detailed_metrics_enabled"]
      logging_level            = route_settings.value["logging_level"]
      route_key                = route_settings.value["route_key"]
      throttling_burst_limit   = route_settings.value["throttling_burst_limit"]
      throttling_rate_limit    = route_settings.value["throttling_rate_limit"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_apigatewayv2_stage.this.arn
}

output "deployment_id" {
  description = "returns a string"
  value       = aws_apigatewayv2_stage.this.deployment_id
}

output "execution_arn" {
  description = "returns a string"
  value       = aws_apigatewayv2_stage.this.execution_arn
}

output "id" {
  description = "returns a string"
  value       = aws_apigatewayv2_stage.this.id
}

output "invoke_url" {
  description = "returns a string"
  value       = aws_apigatewayv2_stage.this.invoke_url
}

output "this" {
  value = aws_apigatewayv2_stage.this
}
```
[top](#index)
