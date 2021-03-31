# hcp_aws_transit_gateway_attachment

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
module "hcp_aws_transit_gateway_attachment" {
  source = "./modules/hcp/d/hcp_aws_transit_gateway_attachment"

  # hvn_id - (required) is a type of string
  hvn_id = null
  # transit_gateway_attachment_id - (required) is a type of string
  transit_gateway_attachment_id = null
  # wait_for_active_state - (optional) is a type of bool
  wait_for_active_state = null

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

variable "transit_gateway_attachment_id" {
  description = "(required) - The user-settable name of the transit gateway attachment in HCP."
  type        = string
}

variable "wait_for_active_state" {
  description = "(optional) - If `true`, Terraform will wait for the transit gateway attachment to reach an `ACTIVE` state before continuing. Default `false`."
  type        = bool
  default     = null
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
data "hcp_aws_transit_gateway_attachment" "this" {
  hvn_id                        = var.hvn_id
  transit_gateway_attachment_id = var.transit_gateway_attachment_id
  wait_for_active_state         = var.wait_for_active_state

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
  value       = data.hcp_aws_transit_gateway_attachment.this.created_at
}

output "destination_cidrs" {
  description = "returns a list of string"
  value       = data.hcp_aws_transit_gateway_attachment.this.destination_cidrs
}

output "expires_at" {
  description = "returns a string"
  value       = data.hcp_aws_transit_gateway_attachment.this.expires_at
}

output "id" {
  description = "returns a string"
  value       = data.hcp_aws_transit_gateway_attachment.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = data.hcp_aws_transit_gateway_attachment.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = data.hcp_aws_transit_gateway_attachment.this.project_id
}

output "provider_transit_gateway_attachment_id" {
  description = "returns a string"
  value       = data.hcp_aws_transit_gateway_attachment.this.provider_transit_gateway_attachment_id
}

output "state" {
  description = "returns a string"
  value       = data.hcp_aws_transit_gateway_attachment.this.state
}

output "transit_gateway_id" {
  description = "returns a string"
  value       = data.hcp_aws_transit_gateway_attachment.this.transit_gateway_id
}

output "this" {
  value = hcp_aws_transit_gateway_attachment.this
}
```

[top](#index)