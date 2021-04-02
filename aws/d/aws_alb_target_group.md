# aws_alb_target_group

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_alb_target_group" {
  source = "./modules/aws/d/aws_alb_target_group"

  # arn - (optional) is a type of string
  arn = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "arn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_alb_target_group" "this" {
  arn  = var.arn
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_alb_target_group.this.arn
}

output "arn_suffix" {
  description = "returns a string"
  value       = data.aws_alb_target_group.this.arn_suffix
}

output "deregistration_delay" {
  description = "returns a number"
  value       = data.aws_alb_target_group.this.deregistration_delay
}

output "health_check" {
  description = "returns a list of object"
  value       = data.aws_alb_target_group.this.health_check
}

output "id" {
  description = "returns a string"
  value       = data.aws_alb_target_group.this.id
}

output "lambda_multi_value_headers_enabled" {
  description = "returns a bool"
  value       = data.aws_alb_target_group.this.lambda_multi_value_headers_enabled
}

output "load_balancing_algorithm_type" {
  description = "returns a string"
  value       = data.aws_alb_target_group.this.load_balancing_algorithm_type
}

output "name" {
  description = "returns a string"
  value       = data.aws_alb_target_group.this.name
}

output "port" {
  description = "returns a number"
  value       = data.aws_alb_target_group.this.port
}

output "preserve_client_ip" {
  description = "returns a string"
  value       = data.aws_alb_target_group.this.preserve_client_ip
}

output "protocol" {
  description = "returns a string"
  value       = data.aws_alb_target_group.this.protocol
}

output "protocol_version" {
  description = "returns a string"
  value       = data.aws_alb_target_group.this.protocol_version
}

output "proxy_protocol_v2" {
  description = "returns a bool"
  value       = data.aws_alb_target_group.this.proxy_protocol_v2
}

output "slow_start" {
  description = "returns a number"
  value       = data.aws_alb_target_group.this.slow_start
}

output "stickiness" {
  description = "returns a list of object"
  value       = data.aws_alb_target_group.this.stickiness
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_alb_target_group.this.tags
}

output "target_type" {
  description = "returns a string"
  value       = data.aws_alb_target_group.this.target_type
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_alb_target_group.this.vpc_id
}

output "this" {
  value = aws_alb_target_group.this
}
```

[top](#index)