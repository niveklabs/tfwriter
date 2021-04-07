# aws_acm_certificate

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
module "aws_acm_certificate" {
  source = "./modules/aws/d/aws_acm_certificate"

  # domain - (required) is a type of string
  domain = null
  # key_types - (optional) is a type of set of string
  key_types = []
  # most_recent - (optional) is a type of bool
  most_recent = null
  # statuses - (optional) is a type of list of string
  statuses = []
  # tags - (optional) is a type of map of string
  tags = {}
  # types - (optional) is a type of list of string
  types = []
}
```

[top](#index)

### Variables

```terraform
variable "domain" {
  description = "(required)"
  type        = string
}

variable "key_types" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "most_recent" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "statuses" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "types" {
  description = "(optional)"
  type        = list(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "aws_acm_certificate" "this" {
  # domain - (required) is a type of string
  domain = var.domain
  # key_types - (optional) is a type of set of string
  key_types = var.key_types
  # most_recent - (optional) is a type of bool
  most_recent = var.most_recent
  # statuses - (optional) is a type of list of string
  statuses = var.statuses
  # tags - (optional) is a type of map of string
  tags = var.tags
  # types - (optional) is a type of list of string
  types = var.types
}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = data.aws_acm_certificate.this.arn
}

output "id" {
  description = "returns a string"
  value       = data.aws_acm_certificate.this.id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_acm_certificate.this.tags
}

output "this" {
  value = aws_acm_certificate.this
}
```

[top](#index)