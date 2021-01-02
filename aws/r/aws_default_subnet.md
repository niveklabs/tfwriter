# aws_default_subnet

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
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_default_subnet" {
  source = "./modules/aws/r/aws_default_subnet"

  # availability_zone - (required) is a type of string
  availability_zone = null
  # map_public_ip_on_launch - (optional) is a type of bool
  map_public_ip_on_launch = null
  # outpost_arn - (optional) is a type of string
  outpost_arn = null
  # tags - (optional) is a type of map of string
  tags = {}

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(required)"
  type        = string
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

```terraform
resource "aws_default_subnet" "this" {
  availability_zone       = var.availability_zone
  map_public_ip_on_launch = var.map_public_ip_on_launch
  outpost_arn             = var.outpost_arn
  tags                    = var.tags

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

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_default_subnet.this.arn
}

output "assign_ipv6_address_on_creation" {
  description = "returns a bool"
  value       = aws_default_subnet.this.assign_ipv6_address_on_creation
}

output "availability_zone_id" {
  description = "returns a string"
  value       = aws_default_subnet.this.availability_zone_id
}

output "cidr_block" {
  description = "returns a string"
  value       = aws_default_subnet.this.cidr_block
}

output "id" {
  description = "returns a string"
  value       = aws_default_subnet.this.id
}

output "ipv6_cidr_block" {
  description = "returns a string"
  value       = aws_default_subnet.this.ipv6_cidr_block
}

output "ipv6_cidr_block_association_id" {
  description = "returns a string"
  value       = aws_default_subnet.this.ipv6_cidr_block_association_id
}

output "map_public_ip_on_launch" {
  description = "returns a bool"
  value       = aws_default_subnet.this.map_public_ip_on_launch
}

output "owner_id" {
  description = "returns a string"
  value       = aws_default_subnet.this.owner_id
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_default_subnet.this.vpc_id
}

output "this" {
  value = aws_default_subnet.this
}
```

[top](#index)