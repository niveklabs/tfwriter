# equinix_network_device

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
module "equinix_network_device" {
  source = "./modules/equinix/r/equinix_network_device"

  # account_number - (required) is a type of string
  account_number = null
  # acl_template_id - (optional) is a type of string
  acl_template_id = null
  # additional_bandwidth - (optional) is a type of number
  additional_bandwidth = null
  # byol - (optional) is a type of bool
  byol = null
  # core_count - (required) is a type of number
  core_count = null
  # hostname - (optional) is a type of string
  hostname = null
  # interface_count - (optional) is a type of number
  interface_count = null
  # license_file - (optional) is a type of string
  license_file = null
  # license_token - (optional) is a type of string
  license_token = null
  # metro_code - (required) is a type of string
  metro_code = null
  # name - (required) is a type of string
  name = null
  # notifications - (required) is a type of set of string
  notifications = []
  # order_reference - (optional) is a type of string
  order_reference = null
  # package_code - (required) is a type of string
  package_code = null
  # purchase_order_number - (optional) is a type of string
  purchase_order_number = null
  # self_managed - (optional) is a type of bool
  self_managed = null
  # term_length - (required) is a type of number
  term_length = null
  # throughput - (optional) is a type of number
  throughput = null
  # throughput_unit - (optional) is a type of string
  throughput_unit = null
  # type_code - (required) is a type of string
  type_code = null
  # vendor_configuration - (optional) is a type of map of string
  vendor_configuration = {}
  # version - (required) is a type of string
  version = null

  secondary_device = [{
    account_number       = null
    acl_template_id      = null
    additional_bandwidth = null
    hostname             = null
    ibx                  = null
    interface = [{
      assigned_type      = null
      id                 = null
      ip_address         = null
      mac_address        = null
      name               = null
      operational_status = null
      status             = null
      type               = null
    }]
    license_file    = null
    license_file_id = null
    license_status  = null
    license_token   = null
    metro_code      = null
    name            = null
    notifications   = []
    redundancy_type = null
    redundant_id    = null
    region          = null
    ssh_ip_address  = null
    ssh_ip_fqdn     = null
    ssh_key = [{
      key_name = null
      username = null
    }]
    status               = null
    uuid                 = null
    vendor_configuration = {}
  }]

  ssh_key = [{
    key_name = null
    username = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "account_number" {
  description = "(required) - Device billing account number"
  type        = string
}

variable "acl_template_id" {
  description = "(optional) - Unique identifier of applied ACL template"
  type        = string
  default     = null
}

variable "additional_bandwidth" {
  description = "(optional) - Additional Internet bandwidth, in Mbps, that will be allocated to the device"
  type        = number
  default     = null
}

variable "byol" {
  description = "(optional) - Boolean value that determines device licensing mode: bring your own license or subscription (default)"
  type        = bool
  default     = null
}

variable "core_count" {
  description = "(required) - Number of CPU cores used by device"
  type        = number
}

variable "hostname" {
  description = "(optional) - Device hostname prefix"
  type        = string
  default     = null
}

variable "interface_count" {
  description = "(optional) - Number of network interfaces on a device. If not specified, default number for a given device type will be used"
  type        = number
  default     = null
}

variable "license_file" {
  description = "(optional) - Path to the license file that will be uploaded and applied on a device, applicable for some device types in BYOL licensing mode"
  type        = string
  default     = null
}

variable "license_token" {
  description = "(optional) - License Token applicable for some device types in BYOL licensing mode"
  type        = string
  default     = null
}

variable "metro_code" {
  description = "(required) - Device location metro code"
  type        = string
}

variable "name" {
  description = "(required) - Device name"
  type        = string
}

variable "notifications" {
  description = "(required) - List of email addresses that will receive device status notifications"
  type        = set(string)
}

variable "order_reference" {
  description = "(optional) - Name/number used to identify device order on the invoice"
  type        = string
  default     = null
}

variable "package_code" {
  description = "(required) - Device software package code"
  type        = string
}

variable "purchase_order_number" {
  description = "(optional) - Purchase order number associated with a device order"
  type        = string
  default     = null
}

variable "self_managed" {
  description = "(optional) - Boolean value that determines device management mode: self-managed or subscription (default)"
  type        = bool
  default     = null
}

variable "term_length" {
  description = "(required) - Device term length"
  type        = number
}

variable "throughput" {
  description = "(optional) - Device license throughput"
  type        = number
  default     = null
}

variable "throughput_unit" {
  description = "(optional) - Device license throughput unit (Mbps or Gbps)"
  type        = string
  default     = null
}

variable "type_code" {
  description = "(required) - Device type code"
  type        = string
}

variable "vendor_configuration" {
  description = "(optional) - Map of vendor specific configuration parameters for a device"
  type        = map(string)
  default     = null
}

variable "version" {
  description = "(required) - Device software software version"
  type        = string
}

variable "secondary_device" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      account_number       = string
      acl_template_id      = string
      additional_bandwidth = number
      hostname             = string
      ibx                  = string
      interface = list(object(
        {
          assigned_type      = string
          id                 = number
          ip_address         = string
          mac_address        = string
          name               = string
          operational_status = string
          status             = string
          type               = string
        }
      ))
      license_file    = string
      license_file_id = string
      license_status  = string
      license_token   = string
      metro_code      = string
      name            = string
      notifications   = set(string)
      redundancy_type = string
      redundant_id    = string
      region          = string
      ssh_ip_address  = string
      ssh_ip_fqdn     = string
      ssh_key = set(object(
        {
          key_name = string
          username = string
        }
      ))
      status               = string
      uuid                 = string
      vendor_configuration = map(string)
    }
  ))
  default = []
}

variable "ssh_key" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      key_name = string
      username = string
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
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "equinix_network_device" "this" {
  # account_number - (required) is a type of string
  account_number = var.account_number
  # acl_template_id - (optional) is a type of string
  acl_template_id = var.acl_template_id
  # additional_bandwidth - (optional) is a type of number
  additional_bandwidth = var.additional_bandwidth
  # byol - (optional) is a type of bool
  byol = var.byol
  # core_count - (required) is a type of number
  core_count = var.core_count
  # hostname - (optional) is a type of string
  hostname = var.hostname
  # interface_count - (optional) is a type of number
  interface_count = var.interface_count
  # license_file - (optional) is a type of string
  license_file = var.license_file
  # license_token - (optional) is a type of string
  license_token = var.license_token
  # metro_code - (required) is a type of string
  metro_code = var.metro_code
  # name - (required) is a type of string
  name = var.name
  # notifications - (required) is a type of set of string
  notifications = var.notifications
  # order_reference - (optional) is a type of string
  order_reference = var.order_reference
  # package_code - (required) is a type of string
  package_code = var.package_code
  # purchase_order_number - (optional) is a type of string
  purchase_order_number = var.purchase_order_number
  # self_managed - (optional) is a type of bool
  self_managed = var.self_managed
  # term_length - (required) is a type of number
  term_length = var.term_length
  # throughput - (optional) is a type of number
  throughput = var.throughput
  # throughput_unit - (optional) is a type of string
  throughput_unit = var.throughput_unit
  # type_code - (required) is a type of string
  type_code = var.type_code
  # vendor_configuration - (optional) is a type of map of string
  vendor_configuration = var.vendor_configuration
  # version - (required) is a type of string
  version = var.version

  dynamic "secondary_device" {
    for_each = var.secondary_device
    content {
      # account_number - (required) is a type of string
      account_number = secondary_device.value["account_number"]
      # acl_template_id - (optional) is a type of string
      acl_template_id = secondary_device.value["acl_template_id"]
      # additional_bandwidth - (optional) is a type of number
      additional_bandwidth = secondary_device.value["additional_bandwidth"]
      # hostname - (optional) is a type of string
      hostname = secondary_device.value["hostname"]
      # license_file - (optional) is a type of string
      license_file = secondary_device.value["license_file"]
      # license_token - (optional) is a type of string
      license_token = secondary_device.value["license_token"]
      # metro_code - (required) is a type of string
      metro_code = secondary_device.value["metro_code"]
      # name - (required) is a type of string
      name = secondary_device.value["name"]
      # notifications - (required) is a type of set of string
      notifications = secondary_device.value["notifications"]
      # vendor_configuration - (optional) is a type of map of string
      vendor_configuration = secondary_device.value["vendor_configuration"]

      dynamic "ssh_key" {
        for_each = secondary_device.value.ssh_key
        content {
          # key_name - (required) is a type of string
          key_name = ssh_key.value["key_name"]
          # username - (required) is a type of string
          username = ssh_key.value["username"]
        }
      }

    }
  }

  dynamic "ssh_key" {
    for_each = var.ssh_key
    content {
      # key_name - (required) is a type of string
      key_name = ssh_key.value["key_name"]
      # username - (required) is a type of string
      username = ssh_key.value["username"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "ibx" {
  description = "returns a string"
  value       = equinix_network_device.this.ibx
}

output "id" {
  description = "returns a string"
  value       = equinix_network_device.this.id
}

output "interface" {
  description = "returns a list of object"
  value       = equinix_network_device.this.interface
}

output "interface_count" {
  description = "returns a number"
  value       = equinix_network_device.this.interface_count
}

output "license_file_id" {
  description = "returns a string"
  value       = equinix_network_device.this.license_file_id
}

output "license_status" {
  description = "returns a string"
  value       = equinix_network_device.this.license_status
}

output "redundancy_type" {
  description = "returns a string"
  value       = equinix_network_device.this.redundancy_type
}

output "redundant_id" {
  description = "returns a string"
  value       = equinix_network_device.this.redundant_id
}

output "region" {
  description = "returns a string"
  value       = equinix_network_device.this.region
}

output "ssh_ip_address" {
  description = "returns a string"
  value       = equinix_network_device.this.ssh_ip_address
}

output "ssh_ip_fqdn" {
  description = "returns a string"
  value       = equinix_network_device.this.ssh_ip_fqdn
}

output "status" {
  description = "returns a string"
  value       = equinix_network_device.this.status
}

output "uuid" {
  description = "returns a string"
  value       = equinix_network_device.this.uuid
}

output "this" {
  value = equinix_network_device.this
}
```

[top](#index)