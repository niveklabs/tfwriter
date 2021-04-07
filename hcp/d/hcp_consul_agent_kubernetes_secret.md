# hcp_consul_agent_kubernetes_secret

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
module "hcp_consul_agent_kubernetes_secret" {
  source = "./modules/hcp/d/hcp_consul_agent_kubernetes_secret"

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

### Datasource

```terraform
data "hcp_consul_agent_kubernetes_secret" "this" {
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
output "id" {
  description = "returns a string"
  value       = data.hcp_consul_agent_kubernetes_secret.this.id
}

output "secret" {
  description = "returns a string"
  value       = data.hcp_consul_agent_kubernetes_secret.this.secret
}

output "this" {
  value = hcp_consul_agent_kubernetes_secret.this
}
```

[top](#index)