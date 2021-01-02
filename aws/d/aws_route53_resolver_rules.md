# aws_route53_resolver_rules

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_route53_resolver_rules" {
  source = "./modules/aws/d/aws_route53_resolver_rules"

  # owner_id - (optional) is a type of string
  owner_id = null
  # resolver_endpoint_id - (optional) is a type of string
  resolver_endpoint_id = null
  # rule_type - (optional) is a type of string
  rule_type = null
  # share_status - (optional) is a type of string
  share_status = null
}
```

[top](#index)

### Variables

```terraform
variable "owner_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resolver_endpoint_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "rule_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "share_status" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_route53_resolver_rules" "this" {
  owner_id             = var.owner_id
  resolver_endpoint_id = var.resolver_endpoint_id
  rule_type            = var.rule_type
  share_status         = var.share_status
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.aws_route53_resolver_rules.this.id
}

output "resolver_rule_ids" {
  description = "returns a set of string"
  value       = data.aws_route53_resolver_rules.this.resolver_rule_ids
}

output "this" {
  value = aws_route53_resolver_rules.this
}
```

[top](#index)