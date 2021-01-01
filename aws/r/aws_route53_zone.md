# aws_route53_zone
[back](../aws.md)
### Index
- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/aws/r/aws_route53_zone"

  # comment - (optional) is a type of string
  comment = null
  # delegation_set_id - (optional) is a type of string
  delegation_set_id = null
  # force_destroy - (optional) is a type of bool
  force_destroy = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  vpc = [{
    vpc_id     = null
    vpc_region = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "delegation_set_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      vpc_id     = string
      vpc_region = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_route53_zone" "this" {
  comment           = var.comment
  delegation_set_id = var.delegation_set_id
  force_destroy     = var.force_destroy
  name              = var.name
  tags              = var.tags

  dynamic "vpc" {
    for_each = var.vpc
    content {
      vpc_id     = vpc.value["vpc_id"]
      vpc_region = vpc.value["vpc_region"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = aws_route53_zone.this.id
}

output "name_servers" {
  description = "returns a list of string"
  value       = aws_route53_zone.this.name_servers
}

output "zone_id" {
  description = "returns a string"
  value       = aws_route53_zone.this.zone_id
}

output "this" {
  value = aws_route53_zone.this
}
```
[top](#index)
