# aws_ec2_local_gateway_virtual_interface
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
module "aws_ec2_local_gateway_virtual_interface" {
  source = "./modules/aws/d/aws_ec2_local_gateway_virtual_interface"

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
data "aws_ec2_local_gateway_virtual_interface" "this" {
  tags = var.tags

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
  value       = data.aws_ec2_local_gateway_virtual_interface.this.id
}

output "local_address" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway_virtual_interface.this.local_address
}

output "local_bgp_asn" {
  description = "returns a number"
  value       = data.aws_ec2_local_gateway_virtual_interface.this.local_bgp_asn
}

output "local_gateway_id" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway_virtual_interface.this.local_gateway_id
}

output "local_gateway_virtual_interface_ids" {
  description = "returns a set of string"
  value       = data.aws_ec2_local_gateway_virtual_interface.this.local_gateway_virtual_interface_ids
}

output "peer_address" {
  description = "returns a string"
  value       = data.aws_ec2_local_gateway_virtual_interface.this.peer_address
}

output "peer_bgp_asn" {
  description = "returns a number"
  value       = data.aws_ec2_local_gateway_virtual_interface.this.peer_bgp_asn
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_ec2_local_gateway_virtual_interface.this.tags
}

output "vlan" {
  description = "returns a number"
  value       = data.aws_ec2_local_gateway_virtual_interface.this.vlan
}

output "this" {
  value = aws_ec2_local_gateway_virtual_interface.this
}
```
[top](#index)
