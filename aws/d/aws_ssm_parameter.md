# aws_ssm_parameter

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
    aws = ">= 3.34.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_ssm_parameter" {
  source = "./modules/aws/d/aws_ssm_parameter"

  # name - (required) is a type of string
  name = null
  # with_decryption - (optional) is a type of bool
  with_decryption = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "with_decryption" {
  description = "(optional)"
  type        = bool
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_ssm_parameter" "this" {
  name            = var.name
  with_decryption = var.with_decryption
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_ssm_parameter.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_ssm_parameter.this.id
}

output "type" {
  description = "returns a string"
  value       = data.aws_ssm_parameter.this.type
}

output "value" {
  description = "returns a string"
  value       = data.aws_ssm_parameter.this.value
  sensitive   = true
}

output "version" {
  description = "returns a number"
  value       = data.aws_ssm_parameter.this.version
}

output "this" {
  value = aws_ssm_parameter.this
}
```

[top](#index)