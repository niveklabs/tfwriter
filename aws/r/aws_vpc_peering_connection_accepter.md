# aws_vpc_peering_connection_accepter

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
    aws = ">= 3.35.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_vpc_peering_connection_accepter" {
  source = "./modules/aws/r/aws_vpc_peering_connection_accepter"

  # auto_accept - (optional) is a type of bool
  auto_accept = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_peering_connection_id - (required) is a type of string
  vpc_peering_connection_id = null

  accepter = [{
    allow_classic_link_to_remote_vpc = null
    allow_remote_vpc_dns_resolution  = null
    allow_vpc_to_remote_classic_link = null
  }]

  requester = [{
    allow_classic_link_to_remote_vpc = null
    allow_remote_vpc_dns_resolution  = null
    allow_vpc_to_remote_classic_link = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_accept" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_peering_connection_id" {
  description = "(required)"
  type        = string
}

variable "accepter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_classic_link_to_remote_vpc = bool
      allow_remote_vpc_dns_resolution  = bool
      allow_vpc_to_remote_classic_link = bool
    }
  ))
  default = []
}

variable "requester" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allow_classic_link_to_remote_vpc = bool
      allow_remote_vpc_dns_resolution  = bool
      allow_vpc_to_remote_classic_link = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_vpc_peering_connection_accepter" "this" {
  auto_accept               = var.auto_accept
  tags                      = var.tags
  vpc_peering_connection_id = var.vpc_peering_connection_id

  dynamic "accepter" {
    for_each = var.accepter
    content {
      allow_classic_link_to_remote_vpc = accepter.value["allow_classic_link_to_remote_vpc"]
      allow_remote_vpc_dns_resolution  = accepter.value["allow_remote_vpc_dns_resolution"]
      allow_vpc_to_remote_classic_link = accepter.value["allow_vpc_to_remote_classic_link"]
    }
  }

  dynamic "requester" {
    for_each = var.requester
    content {
      allow_classic_link_to_remote_vpc = requester.value["allow_classic_link_to_remote_vpc"]
      allow_remote_vpc_dns_resolution  = requester.value["allow_remote_vpc_dns_resolution"]
      allow_vpc_to_remote_classic_link = requester.value["allow_vpc_to_remote_classic_link"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "accept_status" {
  description = "returns a string"
  value       = aws_vpc_peering_connection_accepter.this.accept_status
}

output "id" {
  description = "returns a string"
  value       = aws_vpc_peering_connection_accepter.this.id
}

output "peer_owner_id" {
  description = "returns a string"
  value       = aws_vpc_peering_connection_accepter.this.peer_owner_id
}

output "peer_region" {
  description = "returns a string"
  value       = aws_vpc_peering_connection_accepter.this.peer_region
}

output "peer_vpc_id" {
  description = "returns a string"
  value       = aws_vpc_peering_connection_accepter.this.peer_vpc_id
}

output "vpc_id" {
  description = "returns a string"
  value       = aws_vpc_peering_connection_accepter.this.vpc_id
}

output "this" {
  value = aws_vpc_peering_connection_accepter.this
}
```

[top](#index)