# azurerm_hdinsight_cluster

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    azurerm = ">= 2.54.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_hdinsight_cluster" {
  source = "./modules/azurerm/d/azurerm_hdinsight_cluster"

  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null

  timeouts = [{
    read = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      read = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "azurerm_hdinsight_cluster" "this" {
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # read - (optional) is a type of string
      read = timeouts.value["read"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "cluster_version" {
  description = "returns a string"
  value       = data.azurerm_hdinsight_cluster.this.cluster_version
}

output "component_versions" {
  description = "returns a map of string"
  value       = data.azurerm_hdinsight_cluster.this.component_versions
}

output "edge_ssh_endpoint" {
  description = "returns a string"
  value       = data.azurerm_hdinsight_cluster.this.edge_ssh_endpoint
}

output "gateway" {
  description = "returns a list of object"
  value       = data.azurerm_hdinsight_cluster.this.gateway
}

output "https_endpoint" {
  description = "returns a string"
  value       = data.azurerm_hdinsight_cluster.this.https_endpoint
}

output "id" {
  description = "returns a string"
  value       = data.azurerm_hdinsight_cluster.this.id
}

output "kafka_rest_proxy_endpoint" {
  description = "returns a string"
  value       = data.azurerm_hdinsight_cluster.this.kafka_rest_proxy_endpoint
}

output "kind" {
  description = "returns a string"
  value       = data.azurerm_hdinsight_cluster.this.kind
}

output "location" {
  description = "returns a string"
  value       = data.azurerm_hdinsight_cluster.this.location
}

output "ssh_endpoint" {
  description = "returns a string"
  value       = data.azurerm_hdinsight_cluster.this.ssh_endpoint
}

output "tags" {
  description = "returns a map of string"
  value       = data.azurerm_hdinsight_cluster.this.tags
}

output "tier" {
  description = "returns a string"
  value       = data.azurerm_hdinsight_cluster.this.tier
}

output "tls_min_version" {
  description = "returns a string"
  value       = data.azurerm_hdinsight_cluster.this.tls_min_version
}

output "this" {
  value = azurerm_hdinsight_cluster.this
}
```

[top](#index)