# azurerm_data_factory

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
    azurerm = ">= 2.41.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "azurerm_data_factory" {
  source = "./modules/azurerm/r/azurerm_data_factory"

  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}

  github_configuration = [{
    account_name    = null
    branch_name     = null
    git_url         = null
    repository_name = null
    root_folder     = null
  }]

  identity = [{
    principal_id = null
    tenant_id    = null
    type         = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  vsts_configuration = [{
    account_name    = null
    branch_name     = null
    project_name    = null
    repository_name = null
    root_folder     = null
    tenant_id       = null
  }]
}
```

[top](#index)

### Variables

```terraform
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "github_configuration" {
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

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      principal_id = string
      tenant_id    = string
      type         = string
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

variable "vsts_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account_name    = string
      branch_name     = string
      project_name    = string
      repository_name = string
      root_folder     = string
      tenant_id       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_data_factory" "this" {
  location            = var.location
  name                = var.name
  resource_group_name = var.resource_group_name
  tags                = var.tags

  dynamic "github_configuration" {
    for_each = var.github_configuration
    content {
      account_name    = github_configuration.value["account_name"]
      branch_name     = github_configuration.value["branch_name"]
      git_url         = github_configuration.value["git_url"]
      repository_name = github_configuration.value["repository_name"]
      root_folder     = github_configuration.value["root_folder"]
    }
  }

  dynamic "identity" {
    for_each = var.identity
    content {
      type = identity.value["type"]
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

  dynamic "vsts_configuration" {
    for_each = var.vsts_configuration
    content {
      account_name    = vsts_configuration.value["account_name"]
      branch_name     = vsts_configuration.value["branch_name"]
      project_name    = vsts_configuration.value["project_name"]
      repository_name = vsts_configuration.value["repository_name"]
      root_folder     = vsts_configuration.value["root_folder"]
      tenant_id       = vsts_configuration.value["tenant_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = azurerm_data_factory.this.id
}

output "this" {
  value = azurerm_data_factory.this
}
```

[top](#index)