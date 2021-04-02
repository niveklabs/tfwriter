# aws_alb

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
module "aws_alb" {
  source = "./modules/aws/d/aws_alb"

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
data "aws_alb" "this" {
  arn  = var.arn
  name = var.name
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "access_logs" {
  description = "returns a list of object"
  value       = data.aws_alb.this.access_logs
}

output "arn" {
  description = "returns a string"
  value       = data.aws_alb.this.arn
}

output "arn_suffix" {
  description = "returns a string"
  value       = data.aws_alb.this.arn_suffix
}

output "customer_owned_ipv4_pool" {
  description = "returns a string"
  value       = data.aws_alb.this.customer_owned_ipv4_pool
}

output "dns_name" {
  description = "returns a string"
  value       = data.aws_alb.this.dns_name
}

output "drop_invalid_header_fields" {
  description = "returns a bool"
  value       = data.aws_alb.this.drop_invalid_header_fields
}

output "enable_deletion_protection" {
  description = "returns a bool"
  value       = data.aws_alb.this.enable_deletion_protection
}

output "enable_http2" {
  description = "returns a bool"
  value       = data.aws_alb.this.enable_http2
}

output "id" {
  description = "returns a string"
  value       = data.aws_alb.this.id
}

output "idle_timeout" {
  description = "returns a number"
  value       = data.aws_alb.this.idle_timeout
}

output "internal" {
  description = "returns a bool"
  value       = data.aws_alb.this.internal
}

output "ip_address_type" {
  description = "returns a string"
  value       = data.aws_alb.this.ip_address_type
}

output "load_balancer_type" {
  description = "returns a string"
  value       = data.aws_alb.this.load_balancer_type
}

output "name" {
  description = "returns a string"
  value       = data.aws_alb.this.name
}

output "security_groups" {
  description = "returns a set of string"
  value       = data.aws_alb.this.security_groups
}

output "subnet_mapping" {
  description = "returns a set of object"
  value       = data.aws_alb.this.subnet_mapping
}

output "subnets" {
  description = "returns a set of string"
  value       = data.aws_alb.this.subnets
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_alb.this.tags
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_alb.this.vpc_id
}

output "zone_id" {
  description = "returns a string"
  value       = data.aws_alb.this.zone_id
}

output "this" {
  value = aws_alb.this
}
```

[top](#index)