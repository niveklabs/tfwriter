# aws_api_gateway_stage
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
module "aws_api_gateway_stage" {
  source = "./modules/aws/r/aws_api_gateway_stage"

  # cache_cluster_enabled - (optional) is a type of bool
  cache_cluster_enabled = null
  # cache_cluster_size - (optional) is a type of string
  cache_cluster_size = null
  # client_certificate_id - (optional) is a type of string
  client_certificate_id = null
  # deployment_id - (required) is a type of string
  deployment_id = null
  # description - (optional) is a type of string
  description = null
  # documentation_version - (optional) is a type of string
  documentation_version = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null
  # stage_name - (required) is a type of string
  stage_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # variables - (optional) is a type of map of string
  variables = {}
  # xray_tracing_enabled - (optional) is a type of bool
  xray_tracing_enabled = null

  access_log_settings = [{
    destination_arn = null
    format          = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "cache_cluster_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "cache_cluster_size" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "client_certificate_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deployment_id" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "documentation_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}

variable "stage_name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "variables" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "xray_tracing_enabled" {
  description = "(optional)"
  type        = bool
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
```
[top](#index)

### Resource
```hcl
resource "aws_api_gateway_stage" "this" {
  cache_cluster_enabled = var.cache_cluster_enabled
  cache_cluster_size    = var.cache_cluster_size
  client_certificate_id = var.client_certificate_id
  deployment_id         = var.deployment_id
  description           = var.description
  documentation_version = var.documentation_version
  rest_api_id           = var.rest_api_id
  stage_name            = var.stage_name
  tags                  = var.tags
  variables             = var.variables
  xray_tracing_enabled  = var.xray_tracing_enabled

  dynamic "access_log_settings" {
    for_each = var.access_log_settings
    content {
      destination_arn = access_log_settings.value["destination_arn"]
      format          = access_log_settings.value["format"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_api_gateway_stage.this.arn
}

output "execution_arn" {
  description = "returns a string"
  value       = aws_api_gateway_stage.this.execution_arn
}

output "id" {
  description = "returns a string"
  value       = aws_api_gateway_stage.this.id
}

output "invoke_url" {
  description = "returns a string"
  value       = aws_api_gateway_stage.this.invoke_url
}

output "this" {
  value = aws_api_gateway_stage.this
}
```
[top](#index)
