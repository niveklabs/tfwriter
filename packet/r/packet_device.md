# packet_device

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_device" {
  source = "./modules/packet/r/packet_device"

  # always_pxe - (optional) is a type of bool
  always_pxe = null
  # billing_cycle - (required) is a type of string
  billing_cycle = null
  # custom_data - (optional) is a type of string
  custom_data = null
  # description - (optional) is a type of string
  description = null
  # facilities - (required) is a type of list of string
  facilities = []
  # force_detach_volumes - (optional) is a type of bool
  force_detach_volumes = null
  # hardware_reservation_id - (optional) is a type of string
  hardware_reservation_id = null
  # hostname - (required) is a type of string
  hostname = null
  # ipxe_script_url - (optional) is a type of string
  ipxe_script_url = null
  # operating_system - (required) is a type of string
  operating_system = null
  # plan - (required) is a type of string
  plan = null
  # project_id - (required) is a type of string
  project_id = null
  # project_ssh_key_ids - (optional) is a type of list of string
  project_ssh_key_ids = []
  # storage - (optional) is a type of string
  storage = null
  # tags - (optional) is a type of list of string
  tags = []
  # user_data - (optional) is a type of string
  user_data = null
  # wait_for_reservation_deprovision - (optional) is a type of bool
  wait_for_reservation_deprovision = null

  ip_address = [{
    cidr            = null
    reservation_ids = []
    type            = null
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
variable "always_pxe" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "billing_cycle" {
  description = "(required)"
  type        = string
}

variable "custom_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "facilities" {
  description = "(required)"
  type        = list(string)
}

variable "force_detach_volumes" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "hardware_reservation_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(required)"
  type        = string
}

variable "ipxe_script_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "operating_system" {
  description = "(required)"
  type        = string
}

variable "plan" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "project_ssh_key_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "storage" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "wait_for_reservation_deprovision" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "ip_address" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      cidr            = number
      reservation_ids = list(string)
      type            = string
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
resource "packet_device" "this" {
  # always_pxe - (optional) is a type of bool
  always_pxe = var.always_pxe
  # billing_cycle - (required) is a type of string
  billing_cycle = var.billing_cycle
  # custom_data - (optional) is a type of string
  custom_data = var.custom_data
  # description - (optional) is a type of string
  description = var.description
  # facilities - (required) is a type of list of string
  facilities = var.facilities
  # force_detach_volumes - (optional) is a type of bool
  force_detach_volumes = var.force_detach_volumes
  # hardware_reservation_id - (optional) is a type of string
  hardware_reservation_id = var.hardware_reservation_id
  # hostname - (required) is a type of string
  hostname = var.hostname
  # ipxe_script_url - (optional) is a type of string
  ipxe_script_url = var.ipxe_script_url
  # operating_system - (required) is a type of string
  operating_system = var.operating_system
  # plan - (required) is a type of string
  plan = var.plan
  # project_id - (required) is a type of string
  project_id = var.project_id
  # project_ssh_key_ids - (optional) is a type of list of string
  project_ssh_key_ids = var.project_ssh_key_ids
  # storage - (optional) is a type of string
  storage = var.storage
  # tags - (optional) is a type of list of string
  tags = var.tags
  # user_data - (optional) is a type of string
  user_data = var.user_data
  # wait_for_reservation_deprovision - (optional) is a type of bool
  wait_for_reservation_deprovision = var.wait_for_reservation_deprovision

  dynamic "ip_address" {
    for_each = var.ip_address
    content {
      # cidr - (optional) is a type of number
      cidr = ip_address.value["cidr"]
      # reservation_ids - (optional) is a type of list of string
      reservation_ids = ip_address.value["reservation_ids"]
      # type - (required) is a type of string
      type = ip_address.value["type"]
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
output "access_private_ipv4" {
  description = "returns a string"
  value       = packet_device.this.access_private_ipv4
}

output "access_public_ipv4" {
  description = "returns a string"
  value       = packet_device.this.access_public_ipv4
}

output "access_public_ipv6" {
  description = "returns a string"
  value       = packet_device.this.access_public_ipv6
}

output "created" {
  description = "returns a string"
  value       = packet_device.this.created
}

output "deployed_facility" {
  description = "returns a string"
  value       = packet_device.this.deployed_facility
}

output "deployed_hardware_reservation_id" {
  description = "returns a string"
  value       = packet_device.this.deployed_hardware_reservation_id
}

output "id" {
  description = "returns a string"
  value       = packet_device.this.id
}

output "locked" {
  description = "returns a bool"
  value       = packet_device.this.locked
}

output "network" {
  description = "returns a list of object"
  value       = packet_device.this.network
}

output "network_type" {
  description = "returns a string"
  value       = packet_device.this.network_type
}

output "ports" {
  description = "returns a list of object"
  value       = packet_device.this.ports
}

output "root_password" {
  description = "returns a string"
  value       = packet_device.this.root_password
  sensitive   = true
}

output "ssh_key_ids" {
  description = "returns a list of string"
  value       = packet_device.this.ssh_key_ids
}

output "state" {
  description = "returns a string"
  value       = packet_device.this.state
}

output "updated" {
  description = "returns a string"
  value       = packet_device.this.updated
}

output "this" {
  value = packet_device.this
}
```

[top](#index)