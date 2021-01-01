# aws_route53_zone

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
module "aws_route53_zone" {
  source = "./modules/aws/d/aws_route53_zone"

  # name - (optional) is a type of string
  name = null
  # private_zone - (optional) is a type of bool
  private_zone = null
  # resource_record_set_count - (optional) is a type of number
  resource_record_set_count = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # zone_id - (optional) is a type of string
  zone_id = null
}
```

[top](#index)

### Variables

```hcl
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_zone" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "resource_record_set_count" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```hcl
data "aws_route53_zone" "this" {
  name                      = var.name
  private_zone              = var.private_zone
  resource_record_set_count = var.resource_record_set_count
  tags                      = var.tags
  vpc_id                    = var.vpc_id
  zone_id                   = var.zone_id
}
```

[top](#index)

### Outputs

```hcl
output "caller_reference" {
  description = "returns a string"
  value       = data.aws_route53_zone.this.caller_reference
}

output "comment" {
  description = "returns a string"
  value       = data.aws_route53_zone.this.comment
}

output "id" {
  description = "returns a string"
  value       = data.aws_route53_zone.this.id
}

output "linked_service_description" {
  description = "returns a string"
  value       = data.aws_route53_zone.this.linked_service_description
}

output "linked_service_principal" {
  description = "returns a string"
  value       = data.aws_route53_zone.this.linked_service_principal
}

output "name" {
  description = "returns a string"
  value       = data.aws_route53_zone.this.name
}

output "name_servers" {
  description = "returns a list of string"
  value       = data.aws_route53_zone.this.name_servers
}

output "resource_record_set_count" {
  description = "returns a number"
  value       = data.aws_route53_zone.this.resource_record_set_count
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_route53_zone.this.tags
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_route53_zone.this.vpc_id
}

output "zone_id" {
  description = "returns a string"
  value       = data.aws_route53_zone.this.zone_id
}

output "this" {
  value = aws_route53_zone.this
}
```

[top](#index)