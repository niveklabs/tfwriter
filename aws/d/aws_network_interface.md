# aws_network_interface

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
module "aws_network_interface" {
  source = "./modules/aws/d/aws_network_interface"

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
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```hcl
data "aws_network_interface" "this" {
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
output "association" {
  description = "returns a list of object"
  value       = data.aws_network_interface.this.association
}

output "attachment" {
  description = "returns a list of object"
  value       = data.aws_network_interface.this.attachment
}

output "availability_zone" {
  description = "returns a string"
  value       = data.aws_network_interface.this.availability_zone
}

output "description" {
  description = "returns a string"
  value       = data.aws_network_interface.this.description
}

output "id" {
  description = "returns a string"
  value       = data.aws_network_interface.this.id
}

output "interface_type" {
  description = "returns a string"
  value       = data.aws_network_interface.this.interface_type
}

output "ipv6_addresses" {
  description = "returns a set of string"
  value       = data.aws_network_interface.this.ipv6_addresses
}

output "mac_address" {
  description = "returns a string"
  value       = data.aws_network_interface.this.mac_address
}

output "outpost_arn" {
  description = "returns a string"
  value       = data.aws_network_interface.this.outpost_arn
}

output "owner_id" {
  description = "returns a string"
  value       = data.aws_network_interface.this.owner_id
}

output "private_dns_name" {
  description = "returns a string"
  value       = data.aws_network_interface.this.private_dns_name
}

output "private_ip" {
  description = "returns a string"
  value       = data.aws_network_interface.this.private_ip
}

output "private_ips" {
  description = "returns a list of string"
  value       = data.aws_network_interface.this.private_ips
}

output "requester_id" {
  description = "returns a string"
  value       = data.aws_network_interface.this.requester_id
}

output "security_groups" {
  description = "returns a set of string"
  value       = data.aws_network_interface.this.security_groups
}

output "subnet_id" {
  description = "returns a string"
  value       = data.aws_network_interface.this.subnet_id
}

output "tags" {
  description = "returns a map of string"
  value       = data.aws_network_interface.this.tags
}

output "vpc_id" {
  description = "returns a string"
  value       = data.aws_network_interface.this.vpc_id
}

output "this" {
  value = aws_network_interface.this
}
```

[top](#index)