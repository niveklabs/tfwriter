# aws_api_gateway_method_settings

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_api_gateway_method_settings" {
  source = "./modules/aws/r/aws_api_gateway_method_settings"

  # method_path - (required) is a type of string
  method_path = null
  # rest_api_id - (required) is a type of string
  rest_api_id = null
  # stage_name - (required) is a type of string
  stage_name = null

  settings = [{
    cache_data_encrypted                       = null
    cache_ttl_in_seconds                       = null
    caching_enabled                            = null
    data_trace_enabled                         = null
    logging_level                              = null
    metrics_enabled                            = null
    require_authorization_for_cache_control    = null
    throttling_burst_limit                     = null
    throttling_rate_limit                      = null
    unauthorized_cache_control_header_strategy = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "method_path" {
  description = "(required)"
  type        = string
}

variable "rest_api_id" {
  description = "(required)"
  type        = string
}

variable "stage_name" {
  description = "(required)"
  type        = string
}

variable "settings" {
  description = "nested mode: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      cache_data_encrypted                       = bool
      cache_ttl_in_seconds                       = number
      caching_enabled                            = bool
      data_trace_enabled                         = bool
      logging_level                              = string
      metrics_enabled                            = bool
      require_authorization_for_cache_control    = bool
      throttling_burst_limit                     = number
      throttling_rate_limit                      = number
      unauthorized_cache_control_header_strategy = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_method_settings" "this" {
  method_path = var.method_path
  rest_api_id = var.rest_api_id
  stage_name  = var.stage_name

  dynamic "settings" {
    for_each = var.settings
    content {
      cache_data_encrypted                       = settings.value["cache_data_encrypted"]
      cache_ttl_in_seconds                       = settings.value["cache_ttl_in_seconds"]
      caching_enabled                            = settings.value["caching_enabled"]
      data_trace_enabled                         = settings.value["data_trace_enabled"]
      logging_level                              = settings.value["logging_level"]
      metrics_enabled                            = settings.value["metrics_enabled"]
      require_authorization_for_cache_control    = settings.value["require_authorization_for_cache_control"]
      throttling_burst_limit                     = settings.value["throttling_burst_limit"]
      throttling_rate_limit                      = settings.value["throttling_rate_limit"]
      unauthorized_cache_control_header_strategy = settings.value["unauthorized_cache_control_header_strategy"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_method_settings.this.id
}

output "this" {
  value = aws_api_gateway_method_settings.this
}
```

[top](#index)