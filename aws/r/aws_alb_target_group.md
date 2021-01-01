# aws_alb_target_group

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_alb_target_group" {
  source = "./modules/aws/r/aws_alb_target_group"

  # deregistration_delay - (optional) is a type of number
  deregistration_delay = null
  # lambda_multi_value_headers_enabled - (optional) is a type of bool
  lambda_multi_value_headers_enabled = null
  # load_balancing_algorithm_type - (optional) is a type of string
  load_balancing_algorithm_type = null
  # name - (optional) is a type of string
  name = null
  # name_prefix - (optional) is a type of string
  name_prefix = null
  # port - (optional) is a type of number
  port = null
  # protocol - (optional) is a type of string
  protocol = null
  # proxy_protocol_v2 - (optional) is a type of bool
  proxy_protocol_v2 = null
  # slow_start - (optional) is a type of number
  slow_start = null
  # tags - (optional) is a type of map of string
  tags = {}
  # target_type - (optional) is a type of string
  target_type = null
  # vpc_id - (optional) is a type of string
  vpc_id = null

  health_check = [{
    enabled             = null
    healthy_threshold   = null
    interval            = null
    matcher             = null
    path                = null
    port                = null
    protocol            = null
    timeout             = null
    unhealthy_threshold = null
  }]

  stickiness = [{
    cookie_duration = null
    enabled         = null
    type            = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "deregistration_delay" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "lambda_multi_value_headers_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "load_balancing_algorithm_type" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "protocol" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "proxy_protocol_v2" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "slow_start" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "target_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "health_check" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      enabled             = bool
      healthy_threshold   = number
      interval            = number
      matcher             = string
      path                = string
      port                = string
      protocol            = string
      timeout             = number
      unhealthy_threshold = number
    }
  ))
  default = []
}

variable "stickiness" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      cookie_duration = number
      enabled         = bool
      type            = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_alb_target_group" "this" {
  deregistration_delay               = var.deregistration_delay
  lambda_multi_value_headers_enabled = var.lambda_multi_value_headers_enabled
  load_balancing_algorithm_type      = var.load_balancing_algorithm_type
  name                               = var.name
  name_prefix                        = var.name_prefix
  port                               = var.port
  protocol                           = var.protocol
  proxy_protocol_v2                  = var.proxy_protocol_v2
  slow_start                         = var.slow_start
  tags                               = var.tags
  target_type                        = var.target_type
  vpc_id                             = var.vpc_id

  dynamic "health_check" {
    for_each = var.health_check
    content {
      enabled             = health_check.value["enabled"]
      healthy_threshold   = health_check.value["healthy_threshold"]
      interval            = health_check.value["interval"]
      matcher             = health_check.value["matcher"]
      path                = health_check.value["path"]
      port                = health_check.value["port"]
      protocol            = health_check.value["protocol"]
      timeout             = health_check.value["timeout"]
      unhealthy_threshold = health_check.value["unhealthy_threshold"]
    }
  }

  dynamic "stickiness" {
    for_each = var.stickiness
    content {
      cookie_duration = stickiness.value["cookie_duration"]
      enabled         = stickiness.value["enabled"]
      type            = stickiness.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_alb_target_group.this.arn
}

output "arn_suffix" {
  description = "returns a string"
  value       = aws_alb_target_group.this.arn_suffix
}

output "id" {
  description = "returns a string"
  value       = aws_alb_target_group.this.id
}

output "load_balancing_algorithm_type" {
  description = "returns a string"
  value       = aws_alb_target_group.this.load_balancing_algorithm_type
}

output "name" {
  description = "returns a string"
  value       = aws_alb_target_group.this.name
}

output "this" {
  value = aws_alb_target_group.this
}
```

[top](#index)