# hcp_aws_network_peering

[back](../hcp.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcp = ">= 0.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcp_aws_network_peering" {
  source = "./modules/hcp/r/hcp_aws_network_peering"

  # hvn_id - (required) is a type of string
  hvn_id = null
  # peer_account_id - (required) is a type of string
  peer_account_id = null
  # peer_vpc_cidr_block - (required) is a type of string
  peer_vpc_cidr_block = null
  # peer_vpc_id - (required) is a type of string
  peer_vpc_id = null
  # peer_vpc_region - (required) is a type of string
  peer_vpc_region = null
  # peering_id - (optional) is a type of string
  peering_id = null

  timeouts = [{
    create  = null
    default = null
    delete  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "hvn_id" {
  description = "(required) - The ID of the HashiCorp Virtual Network (HVN)."
  type        = string
}

variable "peer_account_id" {
  description = "(required) - The account ID of the peer VPC in AWS."
  type        = string
}

variable "peer_vpc_cidr_block" {
  description = "(required) - The CIDR range of the peer VPC in AWS."
  type        = string
}

variable "peer_vpc_id" {
  description = "(required) - The ID of the peer VPC in AWS."
  type        = string
}

variable "peer_vpc_region" {
  description = "(required) - The region of the peer VPC in AWS."
  type        = string
}

variable "peering_id" {
  description = "(optional) - The ID of the network peering."
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "hcp_aws_network_peering" "this" {
  hvn_id              = var.hvn_id
  peer_account_id     = var.peer_account_id
  peer_vpc_cidr_block = var.peer_vpc_cidr_block
  peer_vpc_id         = var.peer_vpc_id
  peer_vpc_region     = var.peer_vpc_region
  peering_id          = var.peering_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create  = timeouts.value["create"]
      default = timeouts.value["default"]
      delete  = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = hcp_aws_network_peering.this.created_at
}

output "expires_at" {
  description = "returns a string"
  value       = hcp_aws_network_peering.this.expires_at
}

output "id" {
  description = "returns a string"
  value       = hcp_aws_network_peering.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = hcp_aws_network_peering.this.organization_id
}

output "peering_id" {
  description = "returns a string"
  value       = hcp_aws_network_peering.this.peering_id
}

output "project_id" {
  description = "returns a string"
  value       = hcp_aws_network_peering.this.project_id
}

output "provider_peering_id" {
  description = "returns a string"
  value       = hcp_aws_network_peering.this.provider_peering_id
}

output "this" {
  value = hcp_aws_network_peering.this
}
```

[top](#index)