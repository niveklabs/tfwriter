# signalfx_aws_integration

[back](../signalfx.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    signalfx = ">= 6.7.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "signalfx_aws_integration" {
  source = "./modules/signalfx/r/signalfx_aws_integration"

  # custom_cloudwatch_namespaces - (optional) is a type of set of string
  custom_cloudwatch_namespaces = []
  # enable_aws_usage - (optional) is a type of bool
  enable_aws_usage = null
  # enable_check_large_volume - (optional) is a type of bool
  enable_check_large_volume = null
  # enabled - (required) is a type of bool
  enabled = null
  # external_id - (optional) is a type of string
  external_id = null
  # import_cloud_watch - (optional) is a type of bool
  import_cloud_watch = null
  # integration_id - (required) is a type of string
  integration_id = null
  # key - (optional) is a type of string
  key = null
  # named_token - (optional) is a type of string
  named_token = null
  # poll_rate - (optional) is a type of number
  poll_rate = null
  # regions - (optional) is a type of set of string
  regions = []
  # role_arn - (optional) is a type of string
  role_arn = null
  # services - (optional) is a type of set of string
  services = []
  # token - (optional) is a type of string
  token = null
  # use_get_metric_data_method - (optional) is a type of bool
  use_get_metric_data_method = null

  custom_namespace_sync_rule = [{
    default_action = null
    filter_action  = null
    filter_source  = null
    namespace      = null
  }]

  namespace_sync_rule = [{
    default_action = null
    filter_action  = null
    filter_source  = null
    namespace      = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "custom_cloudwatch_namespaces" {
  description = "(optional) - List of custom AWS CloudWatch namespaces to monitor. Custom namespaces contain custom metrics that you define in AWS; SignalFx imports the metrics so you can monitor them."
  type        = set(string)
  default     = null
}

variable "enable_aws_usage" {
  description = "(optional) - Flag that controls how SignalFx imports usage metrics from AWS to use with AWS Cost Optimizer. If `true`, SignalFx imports the metrics."
  type        = bool
  default     = null
}

variable "enable_check_large_volume" {
  description = "(optional) - Controls how SignalFx checks for large amounts of data for this AWS integration. If true, SignalFx monitors the amount of data coming in from the integration."
  type        = bool
  default     = null
}

variable "enabled" {
  description = "(required) - Whether the integration is enabled or not"
  type        = bool
}

variable "external_id" {
  description = "(optional) - Used with `signalfx_aws_external_integration`. Use this property to specify the external id."
  type        = string
  default     = null
}

variable "import_cloud_watch" {
  description = "(optional) - Flag that controls how SignalFx imports Cloud Watch metrics. If true, SignalFx imports Cloud Watch metrics from AWS."
  type        = bool
  default     = null
}

variable "integration_id" {
  description = "(required) - The ID of this integration"
  type        = string
}

variable "key" {
  description = "(optional) - Used with `signalfx_aws_token_integration`. Use this property to specify the token."
  type        = string
  default     = null
}

variable "named_token" {
  description = "(optional) - A named token to use for ingest"
  type        = string
  default     = null
}

variable "poll_rate" {
  description = "(optional) - AWS poll rate (in seconds). Between `60` and `300`."
  type        = number
  default     = null
}

variable "regions" {
  description = "(optional) - List of AWS regions that SignalFx should monitor."
  type        = set(string)
  default     = null
}

variable "role_arn" {
  description = "(optional) - Used with `signalfx_aws_external_integration`. Use this property to specify the AIM role ARN."
  type        = string
  default     = null
}

variable "services" {
  description = "(optional) - List of AWS services that you want SignalFx to monitor. Each element is a string designating an AWS service."
  type        = set(string)
  default     = null
}

variable "token" {
  description = "(optional) - Used with `signalfx_aws_token_integration`. Use this property to specify the token."
  type        = string
  default     = null
}

variable "use_get_metric_data_method" {
  description = "(optional) - Enables the use of Amazon's GetMetricData API. Defaults to `false`."
  type        = bool
  default     = null
}

variable "custom_namespace_sync_rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      default_action = string
      filter_action  = string
      filter_source  = string
      namespace      = string
    }
  ))
  default = []
}

variable "namespace_sync_rule" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      default_action = string
      filter_action  = string
      filter_source  = string
      namespace      = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "signalfx_aws_integration" "this" {
  custom_cloudwatch_namespaces = var.custom_cloudwatch_namespaces
  enable_aws_usage             = var.enable_aws_usage
  enable_check_large_volume    = var.enable_check_large_volume
  enabled                      = var.enabled
  external_id                  = var.external_id
  import_cloud_watch           = var.import_cloud_watch
  integration_id               = var.integration_id
  key                          = var.key
  named_token                  = var.named_token
  poll_rate                    = var.poll_rate
  regions                      = var.regions
  role_arn                     = var.role_arn
  services                     = var.services
  token                        = var.token
  use_get_metric_data_method   = var.use_get_metric_data_method

  dynamic "custom_namespace_sync_rule" {
    for_each = var.custom_namespace_sync_rule
    content {
      default_action = custom_namespace_sync_rule.value["default_action"]
      filter_action  = custom_namespace_sync_rule.value["filter_action"]
      filter_source  = custom_namespace_sync_rule.value["filter_source"]
      namespace      = custom_namespace_sync_rule.value["namespace"]
    }
  }

  dynamic "namespace_sync_rule" {
    for_each = var.namespace_sync_rule
    content {
      default_action = namespace_sync_rule.value["default_action"]
      filter_action  = namespace_sync_rule.value["filter_action"]
      filter_source  = namespace_sync_rule.value["filter_source"]
      namespace      = namespace_sync_rule.value["namespace"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auth_method" {
  description = "returns a string"
  value       = signalfx_aws_integration.this.auth_method
}

output "id" {
  description = "returns a string"
  value       = signalfx_aws_integration.this.id
}

output "name" {
  description = "returns a string"
  value       = signalfx_aws_integration.this.name
}

output "this" {
  value = signalfx_aws_integration.this
}
```

[top](#index)