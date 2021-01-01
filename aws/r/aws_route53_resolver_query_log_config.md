# aws_route53_resolver_query_log_config

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
module "aws_route53_resolver_query_log_config" {
  source = "./modules/aws/r/aws_route53_resolver_query_log_config"

  # destination_arn - (required) is a type of string
  destination_arn = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```hcl
variable "destination_arn" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "aws_route53_resolver_query_log_config" "this" {
  destination_arn = var.destination_arn
  name            = var.name
  tags            = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_route53_resolver_query_log_config.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_route53_resolver_query_log_config.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_route53_resolver_query_log_config.this.owner_id
}

output "share_status" {
  description = "returns a string"
  value       = aws_route53_resolver_query_log_config.this.share_status
}

output "this" {
  value = aws_route53_resolver_query_log_config.this
}
```

[top](#index)