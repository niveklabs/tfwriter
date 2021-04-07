# hcp_vault_cluster_admin_token

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
module "hcp_vault_cluster_admin_token" {
  source = "./modules/hcp/r/hcp_vault_cluster_admin_token"

  # cluster_id - (required) is a type of string
  cluster_id = null

  timeouts = [{
    create = null
    delete = null
    read   = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - The ID of the HCP Vault cluster."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "hcp_vault_cluster_admin_token" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = hcp_vault_cluster_admin_token.this.created_at
}

output "id" {
  description = "returns a string"
  value       = hcp_vault_cluster_admin_token.this.id
}

output "token" {
  description = "returns a string"
  value       = hcp_vault_cluster_admin_token.this.token
  sensitive   = true
}

output "this" {
  value = hcp_vault_cluster_admin_token.this
}
```

[top](#index)