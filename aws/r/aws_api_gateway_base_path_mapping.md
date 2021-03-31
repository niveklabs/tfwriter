# aws_api_gateway_base_path_mapping

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
module "aws_api_gateway_base_path_mapping" {
  source = "./modules/aws/r/aws_api_gateway_base_path_mapping"

  # api_id - (required) is a type of string
  api_id = null
  # base_path - (optional) is a type of string
  base_path = null
  # domain_name - (required) is a type of string
  domain_name = null
  # stage_name - (optional) is a type of string
  stage_name = null
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(required)"
  type        = string
}

variable "base_path" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "domain_name" {
  description = "(required)"
  type        = string
}

variable "stage_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "aws_api_gateway_base_path_mapping" "this" {
  api_id      = var.api_id
  base_path   = var.base_path
  domain_name = var.domain_name
  stage_name  = var.stage_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aws_api_gateway_base_path_mapping.this.id
}

output "this" {
  value = aws_api_gateway_base_path_mapping.this
}
```

[top](#index)