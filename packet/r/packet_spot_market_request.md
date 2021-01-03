# packet_spot_market_request

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
module "packet_spot_market_request" {
  source = "./modules/packet/r/packet_spot_market_request"

  # devices_max - (required) is a type of number
  devices_max = null
  # devices_min - (required) is a type of number
  devices_min = null
  # facilities - (required) is a type of list of string
  facilities = []
  # max_bid_price - (required) is a type of number
  max_bid_price = null
  # project_id - (required) is a type of string
  project_id = null
  # wait_for_devices - (optional) is a type of bool
  wait_for_devices = null

  instance_parameters = [{
    always_pxe        = null
    billing_cycle     = null
    customdata        = null
    description       = null
    features          = []
    hostname          = null
    ipxe_script_url   = null
    locked            = null
    operating_system  = null
    plan              = null
    project_ssh_keys  = []
    tags              = []
    termintation_time = null
    user_ssh_keys     = []
    userdata          = null
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
variable "devices_max" {
  description = "(required)"
  type        = number
}

variable "devices_min" {
  description = "(required)"
  type        = number
}

variable "facilities" {
  description = "(required)"
  type        = list(string)
}

variable "max_bid_price" {
  description = "(required)"
  type        = number
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "wait_for_devices" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_parameters" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      always_pxe        = bool
      billing_cycle     = string
      customdata        = string
      description       = string
      features          = list(string)
      hostname          = string
      ipxe_script_url   = string
      locked            = string
      operating_system  = string
      plan              = string
      project_ssh_keys  = list(string)
      tags              = list(string)
      termintation_time = string
      user_ssh_keys     = list(string)
      userdata          = string
    }
  ))
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
resource "packet_spot_market_request" "this" {
  devices_max      = var.devices_max
  devices_min      = var.devices_min
  facilities       = var.facilities
  max_bid_price    = var.max_bid_price
  project_id       = var.project_id
  wait_for_devices = var.wait_for_devices

  dynamic "instance_parameters" {
    for_each = var.instance_parameters
    content {
      always_pxe       = instance_parameters.value["always_pxe"]
      billing_cycle    = instance_parameters.value["billing_cycle"]
      customdata       = instance_parameters.value["customdata"]
      description      = instance_parameters.value["description"]
      features         = instance_parameters.value["features"]
      hostname         = instance_parameters.value["hostname"]
      ipxe_script_url  = instance_parameters.value["ipxe_script_url"]
      locked           = instance_parameters.value["locked"]
      operating_system = instance_parameters.value["operating_system"]
      plan             = instance_parameters.value["plan"]
      project_ssh_keys = instance_parameters.value["project_ssh_keys"]
      tags             = instance_parameters.value["tags"]
      user_ssh_keys    = instance_parameters.value["user_ssh_keys"]
      userdata         = instance_parameters.value["userdata"]
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
  value       = packet_spot_market_request.this.id
}

output "this" {
  value = packet_spot_market_request.this
}
```

[top](#index)