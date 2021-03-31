# aws_route53_resolver_rule

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_route53_resolver_rule" {
  source = "./modules/aws/d/aws_route53_resolver_rule"

  # domain_name - (optional) is a type of string
  domain_name = null
  # name - (optional) is a type of string
  name = null
  # resolver_endpoint_id - (optional) is a type of string
  resolver_endpoint_id = null
  # resolver_rule_id - (optional) is a type of string
  resolver_rule_id = null
  # rule_type - (optional) is a type of string
  rule_type = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "domain_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolver_endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolver_rule_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule_type" {
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
data "aws_route53_resolver_rule" "this" {
  domain_name          = var.domain_name
  name                 = var.name
  resolver_endpoint_id = var.resolver_endpoint_id
  resolver_rule_id     = var.resolver_rule_id
  rule_type            = var.rule_type
  tags                 = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_route53_resolver_rule.this.arn
}

output "domain_name" {
  description = "returns a string"
  value       = data.aws_route53_resolver_rule.this.domain_name
}

output "id" {
  description = "returns a string"
  value       = data.aws_route53_resolver_rule.this.id
}

output "name" {
  description = "returns a string"
  value       = data.aws_route53_resolver_rule.this.name
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_route53_resolver_rule.this.owner_id
}

output "resolver_endpoint_id" {
  description = "returns a string"
  value       = data.aws_route53_resolver_rule.this.resolver_endpoint_id
}

output "resolver_rule_id" {
  description = "returns a string"
  value       = data.aws_route53_resolver_rule.this.resolver_rule_id
}

output "rule_type" {
  description = "returns a string"
  value       = data.aws_route53_resolver_rule.this.rule_type
}

output "share_status" {
  description = "returns a string"
  value       = data.aws_route53_resolver_rule.this.share_status
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_route53_resolver_rule.this.tags
}

output "this" {
  value = aws_route53_resolver_rule.this
}
```

[top](#index)