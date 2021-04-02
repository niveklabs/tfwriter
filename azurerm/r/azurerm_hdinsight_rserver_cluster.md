# azurerm_hdinsight_rserver_cluster

[back](../azurerm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "azurerm_hdinsight_rserver_cluster" {
  source = "./modules/azurerm/r/azurerm_hdinsight_rserver_cluster"

  # cluster_version - (required) is a type of string
  cluster_version = null
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # rstudio - (required) is a type of bool
  rstudio = null
  # tags - (optional) is a type of map of string
  tags = {}
  # tier - (required) is a type of string
  tier = null
  # tls_min_version - (optional) is a type of string
  tls_min_version = null

  gateway = [{
    enabled  = null
    password = null
    username = null
  }]

  roles = [{
    edge_node = [{
      password           = null
      ssh_keys           = []
      subnet_id          = null
      username           = null
      virtual_network_id = null
      vm_size            = null
    }]
    head_node = [{
      password           = null
      ssh_keys           = []
      subnet_id          = null
      username           = null
      virtual_network_id = null
      vm_size            = null
    }]
    worker_node = [{
      min_instance_count    = null
      password              = null
      ssh_keys              = []
      subnet_id             = null
      target_instance_count = null
      username              = null
      virtual_network_id    = null
      vm_size               = null
    }]
    zookeeper_node = [{
      password           = null
      ssh_keys           = []
      subnet_id          = null
      username           = null
      virtual_network_id = null
      vm_size            = null
    }]
  }]

  storage_account = [{
    is_default           = null
    storage_account_key  = null
    storage_container_id = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_version" {
  description = "(required)"
  type        = string
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "rstudio" {
  description = "(required)"
  type        = bool
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "tier" {
  description = "(required)"
  type        = string
}

variable "tls_min_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "gateway" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      enabled  = bool
      password = string
      username = string
    }
  ))
}

variable "roles" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      edge_node = list(object(
        {
          password           = string
          ssh_keys           = set(string)
          subnet_id          = string
          username           = string
          virtual_network_id = string
          vm_size            = string
        }
      ))
      head_node = list(object(
        {
          password           = string
          ssh_keys           = set(string)
          subnet_id          = string
          username           = string
          virtual_network_id = string
          vm_size            = string
        }
      ))
      worker_node = list(object(
        {
          min_instance_count    = number
          password              = string
          ssh_keys              = set(string)
          subnet_id             = string
          target_instance_count = number
          username              = string
          virtual_network_id    = string
          vm_size               = string
        }
      ))
      zookeeper_node = list(object(
        {
          password           = string
          ssh_keys           = set(string)
          subnet_id          = string
          username           = string
          virtual_network_id = string
          vm_size            = string
        }
      ))
    }
  ))
}

variable "storage_account" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      is_default           = bool
      storage_account_key  = string
      storage_container_id = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      read   = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_hdinsight_rserver_cluster" "this" {
  cluster_version     = var.cluster_version
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  rstudio             = var.rstudio
  tags                = var.tags
  tier                = var.tier
  tls_min_version     = var.tls_min_version

  dynamic "gateway" {
    for_each = var.gateway
    content {
      enabled  = gateway.value["enabled"]
      password = gateway.value["password"]
      username = gateway.value["username"]
    }
  }

  dynamic "roles" {
    for_each = var.roles
    content {

      dynamic "edge_node" {
        for_each = roles.value.edge_node
        content {
          password           = edge_node.value["password"]
          ssh_keys           = edge_node.value["ssh_keys"]
          subnet_id          = edge_node.value["subnet_id"]
          username           = edge_node.value["username"]
          virtual_network_id = edge_node.value["virtual_network_id"]
          vm_size            = edge_node.value["vm_size"]
        }
      }

      dynamic "head_node" {
        for_each = roles.value.head_node
        content {
          password           = head_node.value["password"]
          ssh_keys           = head_node.value["ssh_keys"]
          subnet_id          = head_node.value["subnet_id"]
          username           = head_node.value["username"]
          virtual_network_id = head_node.value["virtual_network_id"]
          vm_size            = head_node.value["vm_size"]
        }
      }

      dynamic "worker_node" {
        for_each = roles.value.worker_node
        content {
          min_instance_count    = worker_node.value["min_instance_count"]
          password              = worker_node.value["password"]
          ssh_keys              = worker_node.value["ssh_keys"]
          subnet_id             = worker_node.value["subnet_id"]
          target_instance_count = worker_node.value["target_instance_count"]
          username              = worker_node.value["username"]
          virtual_network_id    = worker_node.value["virtual_network_id"]
          vm_size               = worker_node.value["vm_size"]
        }
      }

      dynamic "zookeeper_node" {
        for_each = roles.value.zookeeper_node
        content {
          password           = zookeeper_node.value["password"]
          ssh_keys           = zookeeper_node.value["ssh_keys"]
          subnet_id          = zookeeper_node.value["subnet_id"]
          username           = zookeeper_node.value["username"]
          virtual_network_id = zookeeper_node.value["virtual_network_id"]
          vm_size            = zookeeper_node.value["vm_size"]
        }
      }

    }
  }

  dynamic "storage_account" {
    for_each = var.storage_account
    content {
      is_default           = storage_account.value["is_default"]
      storage_account_key  = storage_account.value["storage_account_key"]
      storage_container_id = storage_account.value["storage_container_id"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "edge_ssh_endpoint" {
  description = "returns a string"
  value       = azurerm_hdinsight_rserver_cluster.this.edge_ssh_endpoint
}

output "https_endpoint" {
  description = "returns a string"
  value       = azurerm_hdinsight_rserver_cluster.this.https_endpoint
}

output "id" {
  description = "returns a string"
  value       = azurerm_hdinsight_rserver_cluster.this.id
}

output "ssh_endpoint" {
  description = "returns a string"
  value       = azurerm_hdinsight_rserver_cluster.this.ssh_endpoint
}

output "this" {
  value = azurerm_hdinsight_rserver_cluster.this
}
```

[top](#index)