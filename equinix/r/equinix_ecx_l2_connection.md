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
    equinix = ">= 1.1.0-beta"
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
    authorization_key   = null
    device_interface_id = null
    device_uuid         = null
    name                = null
    port_uuid           = null
    profile_uuid        = null
    provider_status     = null
    redundancy_type     = null
    redundant_uuid      = null
    seller_metro_code   = null
    seller_region       = null
    speed               = null
    speed_unit          = null
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
  description = "(optional) - Text field used to authorize connection on the provider side. Value depends on a provider service profile used for connection"
  type        = string
  default     = null
}

variable "device_interface_id" {
  description = "(optional) - Identifier of network interface on a given device, used for a connection. If not specified then first available interface will be selected"
  type        = number
  default     = null
}

variable "device_uuid" {
  description = "(optional) - Unique identifier of the Network Edge virtual device from which the connection would originate"
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Connection name. An alpha-numeric 24 characters string which can include only hyphens and underscores"
  type        = string
}

variable "named_tag" {
  description = "(optional) - The type of peering to set up in case when connecting to Azure Express Route. One of Public, Private, Microsoft, Manual"
  type        = string
  default     = null
}

variable "notifications" {
  description = "(required) - A list of email addresses used for sending connection update notifications"
  type        = set(string)
}

variable "port_uuid" {
  description = "(optional) - Unique identifier of the buyer's port from which the connection would originate"
  type        = string
  default     = null
}

variable "profile_uuid" {
  description = "(optional) - Unique identifier of the service provider's service profile"
  type        = string
  default     = null
}

variable "purchase_order_number" {
  description = "(optional) - Connection's purchase order number to reflect on the invoice"
  type        = string
  default     = null
}

variable "seller_metro_code" {
  description = "(optional) - The metro code that denotes the connection’s remote side (z-side)"
  type        = string
  default     = null
}

variable "seller_region" {
  description = "(optional) - The region in which the seller port resides"
  type        = string
  default     = null
}

variable "speed" {
  description = "(required) - Speed/Bandwidth to be allocated to the connection"
  type        = number
}

variable "speed_unit" {
  description = "(required) - Unit of the speed/bandwidth to be allocated to the connection"
  type        = string
}

variable "vlan_ctag" {
  description = "(optional) - C-Tag/Inner-Tag of the connection, a numeric character ranging from 2 - 4094"
  type        = number
  default     = null
}

variable "vlan_stag" {
  description = "(optional) - S-Tag/Outer-Tag of the connection, a numeric character ranging from 2 - 4094"
  type        = number
  default     = null
}

variable "zside_port_uuid" {
  description = "(optional) - Unique identifier of the port on the remote side (z-side)"
  type        = string
  default     = null
}

variable "zside_vlan_ctag" {
  description = "(optional) - C-Tag/Inner-Tag of the connection on the remote side (z-side)"
  type        = number
  default     = null
}

variable "zside_vlan_stag" {
  description = "(optional) - S-Tag/Outer-Tag of the connection on the remote side (z-side)"
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
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      authorization_key   = string
      device_interface_id = number
      device_uuid         = string
      name                = string
      port_uuid           = string
      profile_uuid        = string
      provider_status     = string
      redundancy_type     = string
      redundant_uuid      = string
      seller_metro_code   = string
      seller_region       = string
      speed               = number
      speed_unit          = string
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
      authorization_key   = secondary_connection.value["authorization_key"]
      device_interface_id = secondary_connection.value["device_interface_id"]
      device_uuid         = secondary_connection.value["device_uuid"]
      name                = secondary_connection.value["name"]
      port_uuid           = secondary_connection.value["port_uuid"]
      profile_uuid        = secondary_connection.value["profile_uuid"]
      seller_metro_code   = secondary_connection.value["seller_metro_code"]
      seller_region       = secondary_connection.value["seller_region"]
      speed               = secondary_connection.value["speed"]
      speed_unit          = secondary_connection.value["speed_unit"]
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
output "authorization_key" {
  description = "returns a string"
  value       = equinix_ecx_l2_connection.this.authorization_key
}

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

output "vlan_stag" {
  description = "returns a number"
  value       = equinix_ecx_l2_connection.this.vlan_stag
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