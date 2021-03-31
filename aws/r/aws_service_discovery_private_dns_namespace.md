# aws_service_discovery_private_dns_namespace

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
module "aws_service_discovery_private_dns_namespace" {
  source = "./modules/aws/r/aws_service_discovery_private_dns_namespace"

  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc - (required) is a type of string
  vpc = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "vpc" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_service_discovery_private_dns_namespace" "this" {
  description = var.description
  name        = var.name
  tags        = var.tags
  vpc         = var.vpc
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_service_discovery_private_dns_namespace.this.arn
}

output "hosted_zone" {
  description = "returns a string"
  value       = aws_service_discovery_private_dns_namespace.this.hosted_zone
}

output "id" {
  description = "returns a string"
  value       = aws_service_discovery_private_dns_namespace.this.id
}

output "this" {
  value = aws_service_discovery_private_dns_namespace.this
}
```

[top](#index)