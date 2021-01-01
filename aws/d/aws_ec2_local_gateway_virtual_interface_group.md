# aws_ec2_local_gateway_virtual_interface_group
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
module "aws_ec2_local_gateway_virtual_interface_group" {
  source = "./modules/aws/d/aws_ec2_local_gateway_virtual_interface_group"

  # local_gateway_id - (optional) is a type of string
  local_gateway_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  filter = [{
    name   = null
    values = []
  }]
}
```
[top](#index)
### Variables
```hcl
variable "local_gateway_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "filter" {
  description = "nested mode: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      values = set(string)
    }
  ))
  default = []
}
```
[top](#index)

### Datasource
```hcl
data "aws_ec2_local_gateway_virtual_interface_group" "this" {
  local_gateway_id = var.local_gateway_id
  tags             = var.tags

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      values = filter.value["values"]
    }
  }

}
```
[top](#index)
### Outputs
```hcl
output "id" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway_virtual_interface_group.this.id
}

output "local_gateway_id" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway_virtual_interface_group.this.local_gateway_id
}

output "local_gateway_virtual_interface_ids" {
  description = "returns a set of string"
  value       = data.aws_ec2_local_gateway_virtual_interface_group.this.local_gateway_virtual_interface_ids
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_local_gateway_virtual_interface_group.this.tags
}

output "this" {
  value = aws_ec2_local_gateway_virtual_interface_group.this
}
```
[top](#index)
