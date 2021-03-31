# aws_route53_delegation_set

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
module "aws_route53_delegation_set" {
  source = "./modules/aws/r/aws_route53_delegation_set"

  # reference_name - (optional) is a type of string
  reference_name = null
}
```

[top](#index)

### Variables

```terraform
variable "reference_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_route53_delegation_set" "this" {
  reference_name = var.reference_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_route53_delegation_set.this.id
}

output "name_servers" {
  description = "returns a list of string"
  value       = aws_route53_delegation_set.this.name_servers
}

output "this" {
  value = aws_route53_delegation_set.this
}
```

[top](#index)