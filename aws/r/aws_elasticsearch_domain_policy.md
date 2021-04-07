# aws_elasticsearch_domain_policy

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
module "aws_elasticsearch_domain_policy" {
  source = "./modules/aws/r/aws_elasticsearch_domain_policy"

  # access_policies - (required) is a type of string
  access_policies = null
  # domain_name - (required) is a type of string
  domain_name = null
}
```

[top](#index)

### Variables

```terraform
variable "access_policies" {
  description = "(required)"
  type        = string
}

variable "domain_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_elasticsearch_domain_policy" "this" {
  # access_policies - (required) is a type of string
  access_policies = var.access_policies
  # domain_name - (required) is a type of string
  domain_name = var.domain_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_elasticsearch_domain_policy.this.id
}

output "this" {
  value = aws_elasticsearch_domain_policy.this
}
```

[top](#index)