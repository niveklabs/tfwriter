# hcp_hvn

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
    hcp = ">= 0.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcp_hvn" {
  source = "./modules/hcp/d/hcp_hvn"

  # hvn_id - (required) is a type of string
  hvn_id = null

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
data "hcp_hvn" "this" {
  # hvn_id - (required) is a type of string
  hvn_id = var.hvn_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cidr_block" {
  description = "returns a string"
  value       = data.hcp_hvn.this.cidr_block
}

output "cloud_provider" {
  description = "returns a string"
  value       = data.hcp_hvn.this.cloud_provider
}

output "created_at" {
  description = "returns a string"
  value       = data.hcp_hvn.this.created_at
}

output "id" {
  description = "returns a string"
  value       = data.hcp_hvn.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = data.hcp_hvn.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = data.hcp_hvn.this.project_id
}

output "provider_account_id" {
  description = "returns a string"
  value       = data.hcp_hvn.this.provider_account_id
}

output "region" {
  description = "returns a string"
  value       = data.hcp_hvn.this.region
}

output "this" {
  value = hcp_hvn.this
}
```

[top](#index)