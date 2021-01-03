# equinix_ecx_l2_connection

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.0.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_ecx_l2_connection" {
  source = "./modules/equinix/r/equinix_ecx_l2_connection"

  # authorization_key - (optional) is a type of string
  authorization_key = null
  # device_interface_id - (optional) is a type of number
  device_interface_id = null
  # device_uuid - (optional) is a type of string
  device_uuid = null
  # name - (required) is a type of string
  name = null
  # named_tag - (optional) is a type of string
  named_tag = null
  # notifications - (required) is a type of set of string
  notifications = []
  # port_uuid - (optional) is a type of string
  port_uuid = null
  # profile_uuid - (optional) is a type of string
  profile_uuid = null
  # purchase_order_number - (optional) is a type of string
  purchase_order_number = null
  # seller_metro_code - (optional) is a type of string
  seller_metro_code = null
  # seller_region - (optional) is a type of string
  seller_region = null
  # speed - (required) is a type of number
  speed = null
  # speed_unit - (required) is a type of string
  speed_unit = null
  # vlan_ctag - (optional) is a type of number
  vlan_ctag = null
  # vlan_stag - (optional) is a type of number
  vlan_stag = null
  # zside_port_uuid - (optional) is a type of string
  zside_port_uuid = null
  # zside_vlan_ctag - (optional) is a type of number
  zside_vlan_ctag = null
  # zside_vlan_stag - (optional) is a type of number
  zside_vlan_stag = null

  additional_info = [{
    name  = null
    value = null
  }]

  secondary_connection = [{
    device_interface_id = null
    device_uuid         = null
    name                = null
    port_uuid           = null
    provider_status     = null
    redundancy_type     = null
    redundant_uuid      = null
    status              = null
    uuid                = null
    vlan_ctag           = null
    vlan_stag           = null
    zside_port_uuid     = null
    zside_vlan_ctag     = null
    zside_vlan_stag     = null
  }]

  timeouts = [{
    create = null
    delete = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "authorization_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "device_interface_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "device_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "named_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "notifications" {
  description = "(required)"
  type        = set(string)
}

variable "port_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "purchase_order_number" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "seller_metro_code" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "seller_region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "speed" {
  description = "(required)"
  type        = number
}

variable "speed_unit" {
  description = "(required)"
  type        = string
}

variable "vlan_ctag" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "vlan_stag" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "zside_port_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zside_vlan_ctag" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "zside_vlan_stag" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "additional_info" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}

variable "secondary_connection" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      device_interface_id = number
      device_uuid         = string
      name                = string
      port_uuid           = string
      provider_status     = string
      redundancy_type     = string
      redundant_uuid      = string
      status              = string
      uuid                = string
      vlan_ctag           = number
      vlan_stag           = number
      zside_port_uuid     = string
      zside_vlan_ctag     = number
      zside_vlan_stag     = number
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
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "equinix_ecx_l2_connection" "this" {
  authorization_key     = var.authorization_key
  device_interface_id   = var.device_interface_id
  device_uuid           = var.device_uuid
  name                  = var.name
  named_tag             = var.named_tag
  notifications         = var.notifications
  port_uuid             = var.port_uuid
  profile_uuid          = var.profile_uuid
  purchase_order_number = var.purchase_order_number
  seller_metro_code     = var.seller_metro_code
  seller_region         = var.seller_region
  speed                 = var.speed
  speed_unit            = var.speed_unit
  vlan_ctag             = var.vlan_ctag
  vlan_stag             = var.vlan_stag
  zside_port_uuid       = var.zside_port_uuid
  zside_vlan_ctag       = var.zside_vlan_ctag
  zside_vlan_stag       = var.zside_vlan_stag

  dynamic "additional_info" {
    for_each = var.additional_info
    content {
      name  = additional_info.value["name"]
      value = additional_info.value["value"]
    }
  }

  dynamic "secondary_connection" {
    for_each = var.secondary_connection
    content {
      device_interface_id = secondary_connection.value["device_interface_id"]
      device_uuid         = secondary_connection.value["device_uuid"]
      name                = secondary_connection.value["name"]
      port_uuid           = secondary_connection.value["port_uuid"]
      vlan_ctag           = secondary_connection.value["vlan_ctag"]
      vlan_stag           = secondary_connection.value["vlan_stag"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection.this.id
}

output "profile_uuid" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection.this.profile_uuid
}

output "provider_status" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection.this.provider_status
}

output "redundancy_type" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection.this.redundancy_type
}

output "redundant_uuid" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection.this.redundant_uuid
}

output "seller_metro_code" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection.this.seller_metro_code
}

output "status" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection.this.status
}

output "uuid" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection.this.uuid
}

output "zside_port_uuid" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection.this.zside_port_uuid
}

output "zside_vlan_ctag" {
  description = "returns a number"
  value       = equinix_ecx_l2_connection.this.zside_vlan_ctag
}

output "zside_vlan_stag" {
  description = "returns a number"
  value       = equinix_ecx_l2_connection.this.zside_vlan_stag
}

output "this" {
  value = equinix_ecx_l2_connection.this
}
```

[top](#index)