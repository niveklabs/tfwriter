# hcp_hvn

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
module "hcp_hvn" {
  source = "./modules/hcp/r/hcp_hvn"

  # cidr_block - (optional) is a type of string
  cidr_block = null
  # cloud_provider - (required) is a type of string
  cloud_provider = null
  # hvn_id - (required) is a type of string
  hvn_id = null
  # region - (required) is a type of string
  region = null

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
variable "cidr_block" {
  description = "(optional) - The CIDR range of the HVN. If this is not provided, the service will provide a default value."
  type        = string
  default     = null
}

variable "cloud_provider" {
  description = "(required) - The provider where the HVN is located. Only 'aws' is available at this time."
  type        = string
}

variable "hvn_id" {
  description = "(required) - The ID of the HashiCorp Virtual Network (HVN)."
  type        = string
}

variable "region" {
  description = "(required) - The region where the HVN is located."
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
resource "hcp_hvn" "this" {
  cidr_block     = var.cidr_block
  cloud_provider = var.cloud_provider
  hvn_id         = var.hvn_id
  region         = var.region

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
output "cidr_block" {
  description = "returns a string"
  value       = hcp_hvn.this.cidr_block
}

output "created_at" {
  description = "returns a string"
  value       = hcp_hvn.this.created_at
}

output "id" {
  description = "returns a string"
  value       = hcp_hvn.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = hcp_hvn.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = hcp_hvn.this.project_id
}

output "provider_account_id" {
  description = "returns a string"
  value       = hcp_hvn.this.provider_account_id
}

output "this" {
  value = hcp_hvn.this
}
```

[top](#index)