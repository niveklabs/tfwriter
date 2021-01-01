# aws_ec2_managed_prefix_list
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
module "aws_ec2_managed_prefix_list" {
  source = "./modules/aws/r/aws_ec2_managed_prefix_list"

  # address_family - (required) is a type of string
  address_family = null
  # max_entries - (required) is a type of number
  max_entries = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}

  entry = [{
    cidr        = null
    description = null
  }]
}
```
[top](#index)
### Variables
```hcl
variable "address_family" {
  description = "(required)"
  type        = string
}

variable "max_entries" {
  description = "(required)"
  type        = number
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

variable "entry" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cidr        = string
      description = string
    }
  ))
  default = []
}
```
[top](#index)

### Resource
```hcl
resource "aws_ec2_managed_prefix_list" "this" {
  address_family = var.address_family
  max_entries    = var.max_entries
  name           = var.name
  tags           = var.tags

  dynamic "entry" {
    for_each = var.entry
    content {
      cidr        = entry.value["cidr"]
      description = entry.value["description"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "arn" {
  description = "returns a string"
  value       = aws_ec2_managed_prefix_list.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_ec2_managed_prefix_list.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_ec2_managed_prefix_list.this.owner_id
}

output "version" {
  description = "returns a number"
  value       = aws_ec2_managed_prefix_list.this.version
}

output "this" {
  value = aws_ec2_managed_prefix_list.this
}
```
[top](#index)
