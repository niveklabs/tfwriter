# gridscale_server

[back](../gridscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    gridscale = ">= 1.7.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "gridscale_server" {
  source = "./modules/gridscale/r/gridscale_server"

  # auto_recovery - (optional) is a type of bool
  auto_recovery = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # cores - (required) is a type of number
  cores = null
  # hardware_profile - (optional) is a type of string
  hardware_profile = null
  # ipv4 - (optional) is a type of string
  ipv4 = null
  # ipv6 - (optional) is a type of string
  ipv6 = null
  # isoimage - (optional) is a type of string
  isoimage = null
  # labels - (optional) is a type of set of string
  labels = []
  # memory - (required) is a type of number
  memory = null
  # name - (required) is a type of string
  name = null
  # power - (optional) is a type of bool
  power = null

  network = [{
    bootdevice             = null
    create_time            = null
    firewall_template_uuid = null
    mac                    = null
    network_type           = null
    object_name            = null
    object_uuid            = null
    ordering               = null
    rules_v4_in = [{
      action   = null
      comment  = null
      dst_cidr = null
      dst_port = null
      order    = null
      protocol = null
      src_cidr = null
      src_port = null
    }]
    rules_v4_out = [{
      action   = null
      comment  = null
      dst_cidr = null
      dst_port = null
      order    = null
      protocol = null
      src_cidr = null
      src_port = null
    }]
    rules_v6_in = [{
      action   = null
      comment  = null
      dst_cidr = null
      dst_port = null
      order    = null
      protocol = null
      src_cidr = null
      src_port = null
    }]
    rules_v6_out = [{
      action   = null
      comment  = null
      dst_cidr = null
      dst_port = null
      order    = null
      protocol = null
      src_cidr = null
      src_port = null
    }]
  }]

  storage = [{
    bootdevice         = null
    bus                = null
    capacity           = null
    controller         = null
    create_time        = null
    last_used_template = null
    license_product_no = null
    lun                = null
    object_name        = null
    object_uuid        = null
    storage_type       = null
    target             = null
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
variable "auto_recovery" {
  description = "(optional) - If the server should be auto-started in case of a failure (default=true)."
  type        = bool
  default     = null
}

variable "availability_zone" {
  description = "(optional) - Defines which Availability-Zone the Server is placed."
  type        = string
  default     = null
}

variable "cores" {
  description = "(required) - The number of server cores."
  type        = number
}

variable "hardware_profile" {
  description = "(optional) - The number of server cores."
  type        = string
  default     = null
}

variable "ipv4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "isoimage" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - List of labels."
  type        = set(string)
  default     = null
}

variable "memory" {
  description = "(required) - The amount of server memory in GB."
  type        = number
}

variable "name" {
  description = "(required) - The human-readable name of the object. It supports the full UTF-8 character set, with a maximum of 64 characters"
  type        = string
}

variable "power" {
  description = "(optional) - The number of server cores."
  type        = bool
  default     = null
}

variable "network" {
  description = "nested block: NestingList, min items: 0, max items: 7"
  type = set(object(
    {
      bootdevice             = bool
      create_time            = string
      firewall_template_uuid = string
      mac                    = string
      network_type           = string
      object_name            = string
      object_uuid            = string
      ordering               = number
      rules_v4_in = list(object(
        {
          action   = string
          comment  = string
          dst_cidr = string
          dst_port = string
          order    = number
          protocol = string
          src_cidr = string
          src_port = string
        }
      ))
      rules_v4_out = list(object(
        {
          action   = string
          comment  = string
          dst_cidr = string
          dst_port = string
          order    = number
          protocol = string
          src_cidr = string
          src_port = string
        }
      ))
      rules_v6_in = list(object(
        {
          action   = string
          comment  = string
          dst_cidr = string
          dst_port = string
          order    = number
          protocol = string
          src_cidr = string
          src_port = string
        }
      ))
      rules_v6_out = list(object(
        {
          action   = string
          comment  = string
          dst_cidr = string
          dst_port = string
          order    = number
          protocol = string
          src_cidr = string
          src_port = string
        }
      ))
    }
  ))
  default = []
}

variable "storage" {
  description = "nested block: NestingList, min items: 0, max items: 8"
  type = set(object(
    {
      bootdevice         = bool
      bus                = number
      capacity           = number
      controller         = number
      create_time        = string
      last_used_template = string
      license_product_no = number
      lun                = number
      object_name        = string
      object_uuid        = string
      storage_type       = string
      target             = number
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
resource "gridscale_server" "this" {
  auto_recovery     = var.auto_recovery
  availability_zone = var.availability_zone
  cores             = var.cores
  hardware_profile  = var.hardware_profile
  ipv4              = var.ipv4
  ipv6              = var.ipv6
  isoimage          = var.isoimage
  labels            = var.labels
  memory            = var.memory
  name              = var.name
  power             = var.power

  dynamic "network" {
    for_each = var.network
    content {
      bootdevice             = network.value["bootdevice"]
      firewall_template_uuid = network.value["firewall_template_uuid"]
      object_uuid            = network.value["object_uuid"]
      ordering               = network.value["ordering"]

      dynamic "rules_v4_in" {
        for_each = network.value.rules_v4_in
        content {
          action   = rules_v4_in.value["action"]
          comment  = rules_v4_in.value["comment"]
          dst_cidr = rules_v4_in.value["dst_cidr"]
          dst_port = rules_v4_in.value["dst_port"]
          order    = rules_v4_in.value["order"]
          protocol = rules_v4_in.value["protocol"]
          src_cidr = rules_v4_in.value["src_cidr"]
          src_port = rules_v4_in.value["src_port"]
        }
      }

      dynamic "rules_v4_out" {
        for_each = network.value.rules_v4_out
        content {
          action   = rules_v4_out.value["action"]
          comment  = rules_v4_out.value["comment"]
          dst_cidr = rules_v4_out.value["dst_cidr"]
          dst_port = rules_v4_out.value["dst_port"]
          order    = rules_v4_out.value["order"]
          protocol = rules_v4_out.value["protocol"]
          src_cidr = rules_v4_out.value["src_cidr"]
          src_port = rules_v4_out.value["src_port"]
        }
      }

      dynamic "rules_v6_in" {
        for_each = network.value.rules_v6_in
        content {
          action   = rules_v6_in.value["action"]
          comment  = rules_v6_in.value["comment"]
          dst_cidr = rules_v6_in.value["dst_cidr"]
          dst_port = rules_v6_in.value["dst_port"]
          order    = rules_v6_in.value["order"]
          protocol = rules_v6_in.value["protocol"]
          src_cidr = rules_v6_in.value["src_cidr"]
          src_port = rules_v6_in.value["src_port"]
        }
      }

      dynamic "rules_v6_out" {
        for_each = network.value.rules_v6_out
        content {
          action   = rules_v6_out.value["action"]
          comment  = rules_v6_out.value["comment"]
          dst_cidr = rules_v6_out.value["dst_cidr"]
          dst_port = rules_v6_out.value["dst_port"]
          order    = rules_v6_out.value["order"]
          protocol = rules_v6_out.value["protocol"]
          src_cidr = rules_v6_out.value["src_cidr"]
          src_port = rules_v6_out.value["src_port"]
        }
      }

    }
  }

  dynamic "storage" {
    for_each = var.storage
    content {
      object_uuid = storage.value["object_uuid"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "auto_recovery" {
  description = "returns a bool"
  value       = gridscale_server.this.auto_recovery
}

output "availability_zone" {
  description = "returns a string"
  value       = gridscale_server.this.availability_zone
}

output "change_time" {
  description = "returns a string"
  value       = gridscale_server.this.change_time
}

output "console_token" {
  description = "returns a string"
  value       = gridscale_server.this.console_token
}

output "create_time" {
  description = "returns a string"
  value       = gridscale_server.this.create_time
}

output "current_price" {
  description = "returns a number"
  value       = gridscale_server.this.current_price
}

output "id" {
  description = "returns a string"
  value       = gridscale_server.this.id
}

output "legacy" {
  description = "returns a bool"
  value       = gridscale_server.this.legacy
}

output "location_uuid" {
  description = "returns a string"
  value       = gridscale_server.this.location_uuid
}

output "power" {
  description = "returns a bool"
  value       = gridscale_server.this.power
}

output "status" {
  description = "returns a string"
  value       = gridscale_server.this.status
}

output "usage_in_minutes_cores" {
  description = "returns a number"
  value       = gridscale_server.this.usage_in_minutes_cores
}

output "usage_in_minutes_memory" {
  description = "returns a number"
  value       = gridscale_server.this.usage_in_minutes_memory
}

output "this" {
  value = gridscale_server.this
}
```

[top](#index)