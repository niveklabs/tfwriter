# aws_route53_query_log

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "aws_route53_query_log" {
  source = "./modules/aws/r/aws_route53_query_log"

  # cloudwatch_log_group_arn - (required) is a type of string
  cloudwatch_log_group_arn = null
  # zone_id - (required) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```hcl
variable "cloudwatch_log_group_arn" {
  description = "(required)"
  type        = string
}

variable "zone_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```hcl
resource "aws_route53_query_log" "this" {
  cloudwatch_log_group_arn = var.cloudwatch_log_group_arn
  zone_id                  = var.zone_id
}
```

[top](#index)

### Outputs

```hcl
output "id" {
  description = "returns a string"
  value       = aws_route53_query_log.this.id
}

output "this" {
  value = aws_route53_query_log.this
}
```

[top](#index)