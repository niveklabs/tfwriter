# aws_sagemaker_endpoint

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
module "aws_sagemaker_endpoint" {
  source = "./modules/aws/r/aws_sagemaker_endpoint"

  # endpoint_config_name - (required) is a type of string
  endpoint_config_name = null
  # name - (optional) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "endpoint_config_name" {
  description = "(required)"
  type        = string
}

variable "name" {
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

### Resource

```terraform
resource "aws_sagemaker_endpoint" "this" {
  # endpoint_config_name - (required) is a type of string
  endpoint_config_name = var.endpoint_config_name
  # name - (optional) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_sagemaker_endpoint.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_sagemaker_endpoint.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_sagemaker_endpoint.this.name
}

output "this" {
  value = aws_sagemaker_endpoint.this
}
```

[top](#index)