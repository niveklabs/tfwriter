# aws_wafv2_ip_set

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_wafv2_ip_set" {
  source = "./modules/aws/d/aws_wafv2_ip_set"

  # name - (required) is a type of string
  name = null
  # scope - (required) is a type of string
  scope = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "aws_wafv2_ip_set" "this" {
  name  = var.name
  scope = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "addresses" {
  description = "returns a set of string"
  value       = data.aws_wafv2_ip_set.this.addresses
}

output "arn" {
  description = "returns a string"
  value       = data.aws_wafv2_ip_set.this.arn
}

output "description" {
  description = "returns a string"
  value       = data.aws_wafv2_ip_set.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_wafv2_ip_set.this.id
}

output "ip_address_version" {
  description = "returns a string"
  value       = data.aws_wafv2_ip_set.this.ip_address_version
}

output "this" {
  value = aws_wafv2_ip_set.this
}
```

[top](#index)