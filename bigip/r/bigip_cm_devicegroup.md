# bigip_cm_devicegroup

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_cm_devicegroup" {
  source = "./modules/bigip/r/bigip_cm_devicegroup"

  # auto_sync - (optional) is a type of string
  auto_sync = null
  # description - (optional) is a type of string
  description = null
  # full_load_on_sync - (optional) is a type of string
  full_load_on_sync = null
  # incremental_config - (optional) is a type of number
  incremental_config = null
  # name - (optional) is a type of string
  name = null
  # network_failover - (optional) is a type of string
  network_failover = null
  # partition - (optional) is a type of string
  partition = null
  # save_on_auto_sync - (optional) is a type of string
  save_on_auto_sync = null
  # type - (optional) is a type of string
  type = null

  device = [{
    name            = null
    set_sync_leader = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_sync" {
  description = "(optional) - Specifies if the device-group will automatically sync configuration data to its members"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of Device group"
  type        = string
  default     = null
}

variable "full_load_on_sync" {
  description = "(optional) - Specifies if the device-group will perform a full-load upon sync"
  type        = string
  default     = null
}

variable "incremental_config" {
  description = "(optional) - Specifies the maximum size (in KB) to devote to incremental config sync cached transactions. The default is 1024 KB."
  type        = number
  default     = null
}

variable "name" {
  description = "(optional) - Name of the Device group"
  type        = string
  default     = null
}

variable "network_failover" {
  description = "(optional) - Specifies if the device-group will use a network connection for failover"
  type        = string
  default     = null
}

variable "partition" {
  description = "(optional) - Device administrative partition"
  type        = string
  default     = null
}

variable "save_on_auto_sync" {
  description = "(optional) - Specifies whether the configuration should be saved upon auto-sync."
  type        = string
  default     = null
}

variable "type" {
  description = "(optional) - Specifies if the device-group will be used for failover or resource syncing"
  type        = string
  default     = null
}

variable "device" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name            = string
      set_sync_leader = bool
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "bigip_cm_devicegroup" "this" {
  # auto_sync - (optional) is a type of string
  auto_sync = var.auto_sync
  # description - (optional) is a type of string
  description = var.description
  # full_load_on_sync - (optional) is a type of string
  full_load_on_sync = var.full_load_on_sync
  # incremental_config - (optional) is a type of number
  incremental_config = var.incremental_config
  # name - (optional) is a type of string
  name = var.name
  # network_failover - (optional) is a type of string
  network_failover = var.network_failover
  # partition - (optional) is a type of string
  partition = var.partition
  # save_on_auto_sync - (optional) is a type of string
  save_on_auto_sync = var.save_on_auto_sync
  # type - (optional) is a type of string
  type = var.type

  dynamic "device" {
    for_each = var.device
    content {
      # name - (optional) is a type of string
      name = device.value["name"]
      # set_sync_leader - (optional) is a type of bool
      set_sync_leader = device.value["set_sync_leader"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_cm_devicegroup.this.id
}

output "this" {
  value = bigip_cm_devicegroup.this
}
```

[top](#index)