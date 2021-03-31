# hcp_aws_transit_gateway_attachment

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
    hcp = ">= 0.3.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcp_aws_transit_gateway_attachment" {
  source = "./modules/hcp/r/hcp_aws_transit_gateway_attachment"

  # destination_cidrs - (required) is a type of list of string
  destination_cidrs = []
  # hvn_id - (required) is a type of string
  hvn_id = null
  # resource_share_arn - (required) is a type of string
  resource_share_arn = null
  # transit_gateway_attachment_id - (required) is a type of string
  transit_gateway_attachment_id = null
  # transit_gateway_id - (required) is a type of string
  transit_gateway_id = null

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
variable "destination_cidrs" {
  description = "(required) - The list of associated CIDR ranges. Traffic from these CIDRs will be allowed for all resources in the HVN. Traffic to these CIDRs will be routed into this transit gateway attachment."
  type        = list(string)
}

variable "hvn_id" {
  description = "(required) - The ID of the HashiCorp Virtual Network (HVN)."
  type        = string
}

variable "resource_share_arn" {
  description = "(required) - The Amazon Resource Name (ARN) of the Resource Share that is needed to grant HCP access to the transit gateway in AWS. The Resource Share should be associated with the HCP AWS account principal (see [aws_ram_principal_association](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ram_principal_association)) and the transit gateway resource (see [aws_ram_resource_association](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ram_resource_association))"
  type        = string
}

variable "transit_gateway_attachment_id" {
  description = "(required) - The user-settable name of the transit gateway attachment in HCP."
  type        = string
}

variable "transit_gateway_id" {
  description = "(required) - The ID of the user-owned transit gateway in AWS. The AWS region of the transit gateway must match the HVN."
  type        = string
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
resource "hcp_aws_transit_gateway_attachment" "this" {
  destination_cidrs             = var.destination_cidrs
  hvn_id                        = var.hvn_id
  resource_share_arn            = var.resource_share_arn
  transit_gateway_attachment_id = var.transit_gateway_attachment_id
  transit_gateway_id            = var.transit_gateway_id

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
  value       = hcp_aws_transit_gateway_attachment.this.created_at
}

output "expires_at" {
  description = "returns a string"
  value       = hcp_aws_transit_gateway_attachment.this.expires_at
}

output "id" {
  description = "returns a string"
  value       = hcp_aws_transit_gateway_attachment.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = hcp_aws_transit_gateway_attachment.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = hcp_aws_transit_gateway_attachment.this.project_id
}

output "provider_transit_gateway_attachment_id" {
  description = "returns a string"
  value       = hcp_aws_transit_gateway_attachment.this.provider_transit_gateway_attachment_id
}

output "state" {
  description = "returns a string"
  value       = hcp_aws_transit_gateway_attachment.this.state
}

output "this" {
  value = hcp_aws_transit_gateway_attachment.this
}
```

[top](#index)