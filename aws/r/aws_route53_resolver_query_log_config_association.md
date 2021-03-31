# aws_route53_resolver_query_log_config_association

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_route53_resolver_query_log_config_association" {
  source = "./modules/aws/r/aws_route53_resolver_query_log_config_association"

  # resolver_query_log_config_id - (required) is a type of string
  resolver_query_log_config_id = null
  # resource_id - (required) is a type of string
  resource_id = null
}
```

[top](#index)

### Variables

```terraform
variable "resolver_query_log_config_id" {
  description = "(required)"
  type        = string
}

variable "resource_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_route53_resolver_query_log_config_association" "this" {
  resolver_query_log_config_id = var.resolver_query_log_config_id
  resource_id                  = var.resource_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_route53_resolver_query_log_config_association.this.id
}

output "this" {
  value = aws_route53_resolver_query_log_config_association.this
}
```

[top](#index)