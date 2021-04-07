# aws_route53_resolver_dnssec_config

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_route53_resolver_dnssec_config" {
  source = "./modules/aws/r/aws_route53_resolver_dnssec_config"

  # resource_id - (required) is a type of string
  resource_id = null
}
```

[top](#index)

### Variables

```terraform
variable "resource_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_route53_resolver_dnssec_config" "this" {
  # resource_id - (required) is a type of string
  resource_id = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_route53_resolver_dnssec_config.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_route53_resolver_dnssec_config.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_route53_resolver_dnssec_config.this.owner_id
}

output "validation_status" {
  description = "returns a string"
  value       = aws_route53_resolver_dnssec_config.this.validation_status
}

output "this" {
  value = aws_route53_resolver_dnssec_config.this
}
```

[top](#index)