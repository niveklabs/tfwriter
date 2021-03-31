# aws_cloudwatch_log_destination_policy

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
module "aws_cloudwatch_log_destination_policy" {
  source = "./modules/aws/r/aws_cloudwatch_log_destination_policy"

  # access_policy - (required) is a type of string
  access_policy = null
  # destination_name - (required) is a type of string
  destination_name = null
}
```

[top](#index)

### Variables

```terraform
variable "access_policy" {
  description = "(required)"
  type        = string
}

variable "destination_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "aws_cloudwatch_log_destination_policy" "this" {
  access_policy    = var.access_policy
  destination_name = var.destination_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_cloudwatch_log_destination_policy.this.id
}

output "this" {
  value = aws_cloudwatch_log_destination_policy.this
}
```

[top](#index)