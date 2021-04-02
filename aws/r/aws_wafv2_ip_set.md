# aws_wafv2_ip_set

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
module "aws_wafv2_ip_set" {
  source = "./modules/aws/r/aws_wafv2_ip_set"

  # addresses - (optional) is a type of set of string
  addresses = []
  # description - (optional) is a type of string
  description = null
  # ip_address_version - (required) is a type of string
  ip_address_version = null
  # name - (required) is a type of string
  name = null
  # scope - (required) is a type of string
  scope = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "addresses" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address_version" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
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
resource "aws_wafv2_ip_set" "this" {
  addresses          = var.addresses
  description        = var.description
  ip_address_version = var.ip_address_version
  name               = var.name
  scope              = var.scope
  tags               = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_wafv2_ip_set.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_wafv2_ip_set.this.id
}

output "lock_token" {
  description = "returns a string"
  value       = aws_wafv2_ip_set.this.lock_token
}

output "this" {
  value = aws_wafv2_ip_set.this
}
```

[top](#index)