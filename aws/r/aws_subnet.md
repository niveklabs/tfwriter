# aws_subnet

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
module "aws_subnet" {
  source = "./modules/aws/r/aws_subnet"

  # assign_ipv6_address_on_creation - (optional) is a type of bool
  assign_ipv6_address_on_creation = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # availability_zone_id - (optional) is a type of string
  availability_zone_id = null
  # cidr_block - (required) is a type of string
  cidr_block = null
  # ipv6_cidr_block - (optional) is a type of string
  ipv6_cidr_block = null
  # map_public_ip_on_launch - (optional) is a type of bool
  map_public_ip_on_launch = null
  # outpost_arn - (optional) is a type of string
  outpost_arn = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```hcl
variable "assign_ipv6_address_on_creation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cidr_block" {
  description = "(required)"
  type        = string
}

variable "ipv6_cidr_block" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "map_public_ip_on_launch" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "outpost_arn" {
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
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```hcl
resource "aws_subnet" "this" {
  assign_ipv6_address_on_creation = var.assign_ipv6_address_on_creation
  availability_zone               = var.availability_zone
  availability_zone_id            = var.availability_zone_id
  cidr_block                      = var.cidr_block
  ipv6_cidr_block                 = var.ipv6_cidr_block
  map_public_ip_on_launch         = var.map_public_ip_on_launch
  outpost_arn                     = var.outpost_arn
  tags                            = var.tags
  vpc_id                          = var.vpc_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```hcl
output "arn" {
  description = "returns a string"
  value       = aws_subnet.this.arn
}

output "availability_zone" {
  description = "returns a string"
  value       = aws_subnet.this.availability_zone
}

output "availability_zone_id" {
  description = "returns a string"
  value       = aws_subnet.this.availability_zone_id
}

output "id" {
  description = "returns a string"
  value       = aws_subnet.this.id
}

output "ipv6_cidr_block_association_id" {
  description = "returns a string"
  value       = aws_subnet.this.ipv6_cidr_block_association_id
}

output "owner_id" {
  description = "returns a string"
  value       = aws_subnet.this.owner_id
}

output "this" {
  value = aws_subnet.this
}
```

[top](#index)