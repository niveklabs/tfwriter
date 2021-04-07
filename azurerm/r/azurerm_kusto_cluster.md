# azurerm_kusto_cluster

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
module "azurerm_kusto_cluster" {
  source = "./modules/azurerm/r/azurerm_kusto_cluster"

  # double_encryption_enabled - (optional) is a type of bool
  double_encryption_enabled = null
  # enable_disk_encryption - (optional) is a type of bool
  enable_disk_encryption = null
  # enable_purge - (optional) is a type of bool
  enable_purge = null
  # enable_streaming_ingest - (optional) is a type of bool
  enable_streaming_ingest = null
  # engine - (optional) is a type of string
  engine = null
  # language_extensions - (optional) is a type of list of string
  language_extensions = []
  # location - (required) is a type of string
  location = null
  # name - (required) is a type of string
  name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # tags - (optional) is a type of map of string
  tags = {}
  # trusted_external_tenants - (optional) is a type of list of string
  trusted_external_tenants = []
  # zones - (optional) is a type of list of string
  zones = []

  identity = [{
    identity_ids = []
    principal_id = null
    tenant_id    = null
    type         = null
  }]

  optimized_auto_scale = [{
    maximum_instances = null
    minimum_instances = null
  }]

  sku = [{
    capacity = null
    name     = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  virtual_network_configuration = [{
    data_management_public_ip_id = null
    engine_public_ip_id          = null
    subnet_id                    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "double_encryption_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_disk_encryption" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_purge" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_streaming_ingest" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "engine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "language_extensions" {
  description = "(optional)"
  type        = list(string)
  default     = null
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

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "trusted_external_tenants" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "zones" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "identity" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      identity_ids = set(string)
      principal_id = string
      tenant_id    = string
      type         = string
    }
  ))
  default = []
}

variable "optimized_auto_scale" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      maximum_instances = number
      minimum_instances = number
    }
  ))
  default = []
}

variable "sku" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      capacity = number
      name     = string
    }
  ))
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

variable "virtual_network_configuration" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      data_management_public_ip_id = string
      engine_public_ip_id          = string
      subnet_id                    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "azurerm_kusto_cluster" "this" {
  # double_encryption_enabled - (optional) is a type of bool
  double_encryption_enabled = var.double_encryption_enabled
  # enable_disk_encryption - (optional) is a type of bool
  enable_disk_encryption = var.enable_disk_encryption
  # enable_purge - (optional) is a type of bool
  enable_purge = var.enable_purge
  # enable_streaming_ingest - (optional) is a type of bool
  enable_streaming_ingest = var.enable_streaming_ingest
  # engine - (optional) is a type of string
  engine = var.engine
  # language_extensions - (optional) is a type of list of string
  language_extensions = var.language_extensions
  # location - (required) is a type of string
  location = var.location
  # name - (required) is a type of string
  name = var.name
  # resource_group_name - (required) is a type of string
  resource_group_name = var.resource_group_name
  # tags - (optional) is a type of map of string
  tags = var.tags
  # trusted_external_tenants - (optional) is a type of list of string
  trusted_external_tenants = var.trusted_external_tenants
  # zones - (optional) is a type of list of string
  zones = var.zones

  dynamic "identity" {
    for_each = var.identity
    content {
      # identity_ids - (optional) is a type of set of string
      identity_ids = identity.value["identity_ids"]
      # type - (required) is a type of string
      type = identity.value["type"]
    }
  }

  dynamic "optimized_auto_scale" {
    for_each = var.optimized_auto_scale
    content {
      # maximum_instances - (required) is a type of number
      maximum_instances = optimized_auto_scale.value["maximum_instances"]
      # minimum_instances - (required) is a type of number
      minimum_instances = optimized_auto_scale.value["minimum_instances"]
    }
  }

  dynamic "sku" {
    for_each = var.sku
    content {
      # capacity - (optional) is a type of number
      capacity = sku.value["capacity"]
      # name - (required) is a type of string
      name = sku.value["name"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # read - (optional) is a type of string
      read = timeouts.value["read"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "virtual_network_configuration" {
    for_each = var.virtual_network_configuration
    content {
      # data_management_public_ip_id - (required) is a type of string
      data_management_public_ip_id = virtual_network_configuration.value["data_management_public_ip_id"]
      # engine_public_ip_id - (required) is a type of string
      engine_public_ip_id = virtual_network_configuration.value["engine_public_ip_id"]
      # subnet_id - (required) is a type of string
      subnet_id = virtual_network_configuration.value["subnet_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "data_ingestion_uri" {
  description = "returns a string"
  value       = azurerm_kusto_cluster.this.data_ingestion_uri
}

output "id" {
  description = "returns a string"
  value       = azurerm_kusto_cluster.this.id
}

output "trusted_external_tenants" {
  description = "returns a list of string"
  value       = azurerm_kusto_cluster.this.trusted_external_tenants
}

output "uri" {
  description = "returns a string"
  value       = azurerm_kusto_cluster.this.uri
}

output "this" {
  value = azurerm_kusto_cluster.this
}
```

[top](#index)