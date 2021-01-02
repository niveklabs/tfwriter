# aws_vpc_peering_connection

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
module "aws_vpc_peering_connection" {
  source = "./modules/aws/r/aws_vpc_peering_connection"

  # auto_accept - (optional) is a type of bool
  auto_accept = null
  # peer_owner_id - (optional) is a type of string
  peer_owner_id = null
  # peer_region - (optional) is a type of string
  peer_region = null
  # peer_vpc_id - (required) is a type of string
  peer_vpc_id = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_id - (required) is a type of string
  vpc_id = null

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

  timeouts = [{
    create = null
    delete = null
    update = null
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
  description = "(required)"
  type        = string
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

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aws_vpc_peering_connection" "this" {
  auto_accept   = var.auto_accept
  peer_owner_id = var.peer_owner_id
  peer_region   = var.peer_region
  peer_vpc_id   = var.peer_vpc_id
  tags          = var.tags
  vpc_id        = var.vpc_id

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

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "accept_status" {
  description = "returns a string"
  value       = aws_vpc_peering_connection.this.accept_status
}

output "id" {
  description = "returns a string"
  value       = aws_vpc_peering_connection.this.id
}

output "peer_owner_id" {
  description = "returns a string"
  value       = aws_vpc_peering_connection.this.peer_owner_id
}

output "peer_region" {
  description = "returns a string"
  value       = aws_vpc_peering_connection.this.peer_region
}

output "this" {
  value = aws_vpc_peering_connection.this
}
```

[top](#index)