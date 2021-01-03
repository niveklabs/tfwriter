# azurerm_packet_capture

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
module "azurerm_packet_capture" {
  source = "./modules/azurerm/r/azurerm_packet_capture"

  # maximum_bytes_per_packet - (optional) is a type of number
  maximum_bytes_per_packet = null
  # maximum_bytes_per_session - (optional) is a type of number
  maximum_bytes_per_session = null
  # maximum_capture_duration - (optional) is a type of number
  maximum_capture_duration = null
  # name - (required) is a type of string
  name = null
  # network_watcher_name - (required) is a type of string
  network_watcher_name = null
  # resource_group_name - (required) is a type of string
  resource_group_name = null
  # target_resource_id - (required) is a type of string
  target_resource_id = null

  filter = [{
    local_ip_address  = null
    local_port        = null
    protocol          = null
    remote_ip_address = null
    remote_port       = null
  }]

  storage_location = [{
    file_path          = null
    storage_account_id = null
    storage_path       = null
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
variable "maximum_bytes_per_packet" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_bytes_per_session" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "maximum_capture_duration" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_watcher_name" {
  description = "(required)"
  type        = string
}

variable "resource_group_name" {
  description = "(required)"
  type        = string
}

variable "target_resource_id" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      local_ip_address  = string
      local_port        = string
      protocol          = string
      remote_ip_address = string
      remote_port       = string
    }
  ))
  default = []
}

variable "storage_location" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      file_path          = string
      storage_account_id = string
      storage_path       = string
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
```

[top](#index)

### Resource

```terraform
resource "azurerm_packet_capture" "this" {
  maximum_bytes_per_packet  = var.maximum_bytes_per_packet
  maximum_bytes_per_session = var.maximum_bytes_per_session
  maximum_capture_duration  = var.maximum_capture_duration
  name                      = var.name
  network_watcher_name      = var.network_watcher_name
  resource_group_name       = var.resource_group_name
  target_resource_id        = var.target_resource_id

  dynamic "filter" {
    for_each = var.filter
    content {
      local_ip_address  = filter.value["local_ip_address"]
      local_port        = filter.value["local_port"]
      protocol          = filter.value["protocol"]
      remote_ip_address = filter.value["remote_ip_address"]
      remote_port       = filter.value["remote_port"]
    }
  }

  dynamic "storage_location" {
    for_each = var.storage_location
    content {
      file_path          = storage_location.value["file_path"]
      storage_account_id = storage_location.value["storage_account_id"]
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
output "id" {
  description = "returns a string"
  value       = azurerm_packet_capture.this.id
}

output "this" {
  value = azurerm_packet_capture.this
}
```

[top](#index)