# aws_key_pair

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
module "aws_key_pair" {
  source = "./modules/aws/r/aws_key_pair"

  # key_name - (optional) is a type of string
  key_name = null
  # key_name_prefix - (optional) is a type of string
  key_name_prefix = null
  # public_key - (required) is a type of string
  public_key = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_name_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "public_key" {
  description = "(required)"
  type        = string
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
resource "aws_key_pair" "this" {
  # key_name - (optional) is a type of string
  key_name = var.key_name
  # key_name_prefix - (optional) is a type of string
  key_name_prefix = var.key_name_prefix
  # public_key - (required) is a type of string
  public_key = var.public_key
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_key_pair.this.arn
}

output "fingerprint" {
  description = "returns a string"
  value       = aws_key_pair.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = aws_key_pair.this.id
}

output "key_name" {
  description = "returns a string"
  value       = aws_key_pair.this.key_name
}

output "key_pair_id" {
  description = "returns a string"
  value       = aws_key_pair.this.key_pair_id
}

output "this" {
  value = aws_key_pair.this
}
```

[top](#index)