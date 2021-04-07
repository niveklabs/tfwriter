# hcp_consul_cluster_root_token

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
module "hcp_consul_cluster_root_token" {
  source = "./modules/hcp/r/hcp_consul_cluster_root_token"

  # cluster_id - (required) is a type of string
  cluster_id = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - The ID of the HCP Consul cluster."
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

### Resource

```terraform
resource "hcp_consul_cluster_root_token" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id

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
output "accessor_id" {
  description = "returns a string"
  value       = hcp_consul_cluster_root_token.this.accessor_id
}

output "id" {
  description = "returns a string"
  value       = hcp_consul_cluster_root_token.this.id
}

output "kubernetes_secret" {
  description = "returns a string"
  value       = hcp_consul_cluster_root_token.this.kubernetes_secret
  sensitive   = true
}

output "secret_id" {
  description = "returns a string"
  value       = hcp_consul_cluster_root_token.this.secret_id
  sensitive   = true
}

output "this" {
  value = hcp_consul_cluster_root_token.this
}
```

[top](#index)