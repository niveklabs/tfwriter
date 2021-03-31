# hcp_aws_network_peering

[back](../hcp.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcp = ">= 0.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcp_aws_network_peering" {
  source = "./modules/hcp/d/hcp_aws_network_peering"

  # hvn_id - (required) is a type of string
  hvn_id = null
  # peering_id - (required) is a type of string
  peering_id = null

  timeouts = [{
    default = null
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

variable "peering_id" {
  description = "(required) - The ID of the Network peering."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "hcp_aws_network_peering" "this" {
  hvn_id     = var.hvn_id
  peering_id = var.peering_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.hcp_aws_network_peering.this.created_at
}

output "expires_at" {
  description = "returns a string"
  value       = data.hcp_aws_network_peering.this.expires_at
}

output "id" {
  description = "returns a string"
  value       = data.hcp_aws_network_peering.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = data.hcp_aws_network_peering.this.organization_id
}

output "peer_account_id" {
  description = "returns a string"
  value       = data.hcp_aws_network_peering.this.peer_account_id
}

output "peer_vpc_cidr_block" {
  description = "returns a string"
  value       = data.hcp_aws_network_peering.this.peer_vpc_cidr_block
}

output "peer_vpc_id" {
  description = "returns a string"
  value       = data.hcp_aws_network_peering.this.peer_vpc_id
}

output "peer_vpc_region" {
  description = "returns a string"
  value       = data.hcp_aws_network_peering.this.peer_vpc_region
}

output "project_id" {
  description = "returns a string"
  value       = data.hcp_aws_network_peering.this.project_id
}

output "provider_peering_id" {
  description = "returns a string"
  value       = data.hcp_aws_network_peering.this.provider_peering_id
}

output "this" {
  value = hcp_aws_network_peering.this
}
```

[top](#index)