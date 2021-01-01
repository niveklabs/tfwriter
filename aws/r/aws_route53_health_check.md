# aws_route53_health_check

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
module "aws_route53_health_check" {
  source = "./modules/aws/r/aws_route53_health_check"

  # child_health_threshold - (optional) is a type of number
  child_health_threshold = null
  # child_healthchecks - (optional) is a type of set of string
  child_healthchecks = []
  # cloudwatch_alarm_name - (optional) is a type of string
  cloudwatch_alarm_name = null
  # cloudwatch_alarm_region - (optional) is a type of string
  cloudwatch_alarm_region = null
  # disabled - (optional) is a type of bool
  disabled = null
  # enable_sni - (optional) is a type of bool
  enable_sni = null
  # failure_threshold - (optional) is a type of number
  failure_threshold = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # insufficient_data_health_status - (optional) is a type of string
  insufficient_data_health_status = null
  # invert_healthcheck - (optional) is a type of bool
  invert_healthcheck = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # measure_latency - (optional) is a type of bool
  measure_latency = null
  # port - (optional) is a type of number
  port = null
  # reference_name - (optional) is a type of string
  reference_name = null
  # regions - (optional) is a type of set of string
  regions = []
  # request_interval - (optional) is a type of number
  request_interval = null
  # resource_path - (optional) is a type of string
  resource_path = null
  # search_string - (optional) is a type of string
  search_string = null
  # tags - (optional) is a type of map of string
  tags = {}
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```hcl
variable "child_health_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "child_healthchecks" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "cloudwatch_alarm_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cloudwatch_alarm_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_sni" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "failure_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "insufficient_data_health_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "invert_healthcheck" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "measure_latency" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "reference_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "regions" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "request_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "resource_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "search_string" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_route53_health_check" "this" {
  child_health_threshold          = var.child_health_threshold
  child_healthchecks              = var.child_healthchecks
  cloudwatch_alarm_name           = var.cloudwatch_alarm_name
  cloudwatch_alarm_region         = var.cloudwatch_alarm_region
  disabled                        = var.disabled
  enable_sni                      = var.enable_sni
  failure_threshold               = var.failure_threshold
  fqdn                            = var.fqdn
  insufficient_data_health_status = var.insufficient_data_health_status
  invert_healthcheck              = var.invert_healthcheck
  ip_address                      = var.ip_address
  measure_latency                 = var.measure_latency
  port                            = var.port
  reference_name                  = var.reference_name
  regions                         = var.regions
  request_interval                = var.request_interval
  resource_path                   = var.resource_path
  search_string                   = var.search_string
  tags                            = var.tags
  type                            = var.type
}
```

[top](#index)

### Outputs

```hcl
output "enable_sni" {
  description = "returns a bool"
  value       = aws_route53_health_check.this.enable_sni
}

output "id" {
  description = "returns a string"
  value       = aws_route53_health_check.this.id
}

output "this" {
  value = aws_route53_health_check.this
}
```

[top](#index)