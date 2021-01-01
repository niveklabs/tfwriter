# aws_vpc_peering_connection
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
module "aws_vpc_peering_connection" {
  source = "./modules/aws/d/aws_vpc_peering_connection"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # owner_id - (optional) is a type of string
  owner_id = null
  # peer_cidr_block - (optional) is a type of string
  peer_cidr_block = null
  # peer_owner_id - (optional) is a type of string
  peer_owner_id = null
  # peer_region - (optional) is a type of string
  peer_region = null
  # peer_vpc_id - (optional) is a type of string
  peer_vpc_id = null
  # region - (optional) is a type of string
  region = null
  # status - (optional) is a type of string
  status = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (optional) is a type of string
  vpc_id = null

  filter = [{
    name   = null
    values = []
  }]
}
```
[top](#index)
### Variables
```hcl
variable "cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "owner_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_owner_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "status" {
  description = "(optional)"
  type        = string
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
data "aws_vpc_peering_connection" "this" {
  cidr_block      = var.cidr_block
  owner_id        = var.owner_id
  peer_cidr_block = var.peer_cidr_block
  peer_owner_id   = var.peer_owner_id
  peer_region     = var.peer_region
  peer_vpc_id     = var.peer_vpc_id
  region          = var.region
  status          = var.status
  tags            = var.tags
  vpc_id          = var.vpc_id

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
output "accepter" {
  description = "returns a map of bool"
  value       = data.aws_vpc_peering_connection.this.accepter
}

output "cidr_block" {
  description = "returns a string"
  value       = data.aws_vpc_peering_connection.this.cidr_block
}

output "id" {
  description = "returns a string"
  value       = data.aws_vpc_peering_connection.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_vpc_peering_connection.this.owner_id
}

output "peer_cidr_block" {
  description = "returns a string"
  value       = data.aws_vpc_peering_connection.this.peer_cidr_block
}

output "peer_owner_id" {
  description = "returns a string"
  value       = data.aws_vpc_peering_connection.this.peer_owner_id
}

output "peer_region" {
  description = "returns a string"
  value       = data.aws_vpc_peering_connection.this.peer_region
}

output "peer_vpc_id" {
  description = "returns a string"
  value       = data.aws_vpc_peering_connection.this.peer_vpc_id
}

output "region" {
  description = "returns a string"
  value       = data.aws_vpc_peering_connection.this.region
}

output "requester" {
  description = "returns a map of bool"
  value       = data.aws_vpc_peering_connection.this.requester
}

output "status" {
  description = "returns a string"
  value       = data.aws_vpc_peering_connection.this.status
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_vpc_peering_connection.this.tags
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_vpc_peering_connection.this.vpc_id
}

output "this" {
  value = aws_vpc_peering_connection.this
}
```
[top](#index)
