# azurerm_synapse_workspace

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
module "azurerm_synapse_workspace" {
  source = "./modules/azurerm/r/azurerm_synapse_workspace"

  # aad_admin - (optional) is a type of list of object
  aad_admin = [{
    login     = null
    object_id = null
    tenant_id = null
  }]
  # location - (required) is a type of string
  location = null
  # managed_resource_group_name - (optional) is a type of string
  managed_resource_group_name = null
  # managed_virtual_network_enabled - (optional) is a type of bool
  managed_virtual_network_enabled = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # sql_administrator_login - (required) is a type of string
  sql_administrator_login = null
  # sql_administrator_login_password - (required) is a type of string
  sql_administrator_login_password = null
  # sql_identity_control_enabled - (optional) is a type of bool
  sql_identity_control_enabled = null
  # storage_data_lake_gen2_filesystem_id - (required) is a type of string
  storage_data_lake_gen2_filesystem_id = null
  # tags - (optional) is a type of map of string
  tags = {}

  azure_devops_repo = [{
    account_name    = null
    branch_name     = null
    project_name    = null
    repository_name = null
    root_folder     = null
  }]

  github_repo = [{
    account_name    = null
    branch_name     = null
    git_url         = null
    repository_name = null
    root_folder     = null
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
variable "aad_admin" {
  description = "(optional)"
  type = list(object(
    {
      login     = string
      object_id = string
      tenant_id = string
    }
  ))
  default = null
}

variable "location" {
  description = "(required)"
  type        = string
}

variable "managed_resource_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "managed_virtual_network_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "sql_administrator_login" {
  description = "(required)"
  type        = string
}

variable "sql_administrator_login_password" {
  description = "(required)"
  type        = string
}

variable "sql_identity_control_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "storage_data_lake_gen2_filesystem_id" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "azure_devops_repo" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account_name    = string
      branch_name     = string
      project_name    = string
      repository_name = string
      root_folder     = string
    }
  ))
  default = []
}

variable "github_repo" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account_name    = string
      branch_name     = string
      git_url         = string
      repository_name = string
      root_folder     = string
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
resource "azurerm_synapse_workspace" "this" {
  aad_admin                            = var.aad_admin
  location                             = var.location
  managed_resource_group_name          = var.managed_resource_group_name
  managed_virtual_network_enabled      = var.managed_virtual_network_enabled
  name                                 = var.name
  resource_group_name                  = var.resource_group_name
  sql_administrator_login              = var.sql_administrator_login
  sql_administrator_login_password     = var.sql_administrator_login_password
  sql_identity_control_enabled         = var.sql_identity_control_enabled
  storage_data_lake_gen2_filesystem_id = var.storage_data_lake_gen2_filesystem_id
  tags                                 = var.tags

  dynamic "azure_devops_repo" {
    for_each = var.azure_devops_repo
    content {
      account_name    = azure_devops_repo.value["account_name"]
      branch_name     = azure_devops_repo.value["branch_name"]
      project_name    = azure_devops_repo.value["project_name"]
      repository_name = azure_devops_repo.value["repository_name"]
      root_folder     = azure_devops_repo.value["root_folder"]
    }
  }

  dynamic "github_repo" {
    for_each = var.github_repo
    content {
      account_name    = github_repo.value["account_name"]
      branch_name     = github_repo.value["branch_name"]
      git_url         = github_repo.value["git_url"]
      repository_name = github_repo.value["repository_name"]
      root_folder     = github_repo.value["root_folder"]
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
output "aad_admin" {
  description = "returns a list of object"
  value       = azurerm_synapse_workspace.this.aad_admin
}

output "connectivity_endpoints" {
  description = "returns a map of string"
  value       = azurerm_synapse_workspace.this.connectivity_endpoints
}

output "id" {
  description = "returns a string"
  value       = azurerm_synapse_workspace.this.id
}

output "identity" {
  description = "returns a list of object"
  value       = azurerm_synapse_workspace.this.identity
}

output "managed_resource_group_name" {
  description = "returns a string"
  value       = azurerm_synapse_workspace.this.managed_resource_group_name
}

output "this" {
  value = azurerm_synapse_workspace.this
}
```

[top](#index)