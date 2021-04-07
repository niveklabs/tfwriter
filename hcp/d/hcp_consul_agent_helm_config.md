# hcp_consul_agent_helm_config

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
module "hcp_consul_agent_helm_config" {
  source = "./modules/hcp/d/hcp_consul_agent_helm_config"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # expose_gossip_ports - (optional) is a type of bool
  expose_gossip_ports = null
  # kubernetes_endpoint - (required) is a type of string
  kubernetes_endpoint = null

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

variable "expose_gossip_ports" {
  description = "(optional) - Denotes that the gossip ports should be exposed."
  type        = bool
  default     = null
}

variable "kubernetes_endpoint" {
  description = "(required) - The FQDN for the Kubernetes API."
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
data "hcp_consul_agent_helm_config" "this" {
  # cluster_id - (required) is a type of string
  cluster_id = var.cluster_id
  # expose_gossip_ports - (optional) is a type of bool
  expose_gossip_ports = var.expose_gossip_ports
  # kubernetes_endpoint - (required) is a type of string
  kubernetes_endpoint = var.kubernetes_endpoint

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
output "config" {
  description = "returns a string"
  value       = data.hcp_consul_agent_helm_config.this.config
}

output "id" {
  description = "returns a string"
  value       = data.hcp_consul_agent_helm_config.this.id
}

output "this" {
  value = hcp_consul_agent_helm_config.this
}
```

[top](#index)