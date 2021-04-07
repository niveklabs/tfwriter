# hcs_agent_helm_config

[back](../hcs.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcs = ">= 0.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcs_agent_helm_config" {
  source = "./modules/hcs/d/hcs_agent_helm_config"

  # aks_cluster_name - (required) is a type of string
  aks_cluster_name = null
  # aks_resource_group - (optional) is a type of string
  aks_resource_group = null
  # expose_gossip_ports - (optional) is a type of bool
  expose_gossip_ports = null
  # managed_application_name - (required) is a type of string
  managed_application_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "aks_cluster_name" {
  description = "(required) - The name of the AKS cluster that will consume the Helm config."
  type        = string
}

variable "aks_resource_group" {
  description = "(optional) - The resource group name of the AKS cluster that will consume the Helm config. If not specified, it is defaulted to the value of `resource_group_name`."
  type        = string
  default     = null
}

variable "expose_gossip_ports" {
  description = "(optional) - Denotes that the gossip ports should be exposed. Defaults to `false`."
  type        = bool
  default     = null
}

variable "managed_application_name" {
  description = "(required) - The name of the HCS Azure Managed Application."
  type        = string
}

variable "resource_group_name" {
  description = "(required) - The name of the Resource Group in which the HCS Azure Managed Application belongs."
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
data "hcs_agent_helm_config" "this" {
  # aks_cluster_name - (required) is a type of string
  aks_cluster_name = var.aks_cluster_name
  # aks_resource_group - (optional) is a type of string
  aks_resource_group = var.aks_resource_group
  # expose_gossip_ports - (optional) is a type of bool
  expose_gossip_ports = var.expose_gossip_ports
  # managed_application_name - (required) is a type of string
  managed_application_name = var.managed_application_name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

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
  value       = data.hcs_agent_helm_config.this.config
}

output "id" {
  description = "returns a string"
  value       = data.hcs_agent_helm_config.this.id
}

output "this" {
  value = hcs_agent_helm_config.this
}
```

[top](#index)