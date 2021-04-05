# thunder_overlay_tunnel_vtep

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_overlay_tunnel_vtep" {
  source = "./modules/thunder/r/thunder_overlay_tunnel_vtep"

  # encap - (optional) is a type of string
  encap = null
  # id2 - (optional) is a type of number
  id2 = null
  # user_tag - (optional) is a type of string
  user_tag = null
  # uuid - (optional) is a type of string
  uuid = null

  destination_ip_address_list = [{
    encap      = null
    ip_address = null
    user_tag   = null
    uuid       = null
    vni_list = [{
      segment = null
      uuid    = null
    }]
  }]

  host_list = [{
    destination_vtep = null
    ip_addr          = null
    overlay_mac_addr = null
    uuid             = null
    vni              = null
  }]

  sampling_enable = [{
    counters1 = null
  }]

  source_ip_address = [{
    ip_address = null
    uuid       = null
    vni_list = [{
      segment = null
      uuid    = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "encap" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "id2" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "destination_ip_address_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      encap      = string
      ip_address = string
      user_tag   = string
      uuid       = string
      vni_list = list(object(
        {
          segment = number
          uuid    = string
        }
      ))
    }
  ))
  default = []
}

variable "host_list" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      destination_vtep = string
      ip_addr          = string
      overlay_mac_addr = string
      uuid             = string
      vni              = number
    }
  ))
  default = []
}

variable "sampling_enable" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      counters1 = string
    }
  ))
  default = []
}

variable "source_ip_address" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ip_address = string
      uuid       = string
      vni_list = list(object(
        {
          segment = number
          uuid    = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_overlay_tunnel_vtep" "this" {
  encap    = var.encap
  id2      = var.id2
  user_tag = var.user_tag
  uuid     = var.uuid

  dynamic "destination_ip_address_list" {
    for_each = var.destination_ip_address_list
    content {
      encap      = destination_ip_address_list.value["encap"]
      ip_address = destination_ip_address_list.value["ip_address"]
      user_tag   = destination_ip_address_list.value["user_tag"]
      uuid       = destination_ip_address_list.value["uuid"]

      dynamic "vni_list" {
        for_each = destination_ip_address_list.value.vni_list
        content {
          segment = vni_list.value["segment"]
          uuid    = vni_list.value["uuid"]
        }
      }

    }
  }

  dynamic "host_list" {
    for_each = var.host_list
    content {
      destination_vtep = host_list.value["destination_vtep"]
      ip_addr          = host_list.value["ip_addr"]
      overlay_mac_addr = host_list.value["overlay_mac_addr"]
      uuid             = host_list.value["uuid"]
      vni              = host_list.value["vni"]
    }
  }

  dynamic "sampling_enable" {
    for_each = var.sampling_enable
    content {
      counters1 = sampling_enable.value["counters1"]
    }
  }

  dynamic "source_ip_address" {
    for_each = var.source_ip_address
    content {
      ip_address = source_ip_address.value["ip_address"]
      uuid       = source_ip_address.value["uuid"]

      dynamic "vni_list" {
        for_each = source_ip_address.value.vni_list
        content {
          segment = vni_list.value["segment"]
          uuid    = vni_list.value["uuid"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_overlay_tunnel_vtep.this.id
}

output "this" {
  value = thunder_overlay_tunnel_vtep.this
}
```

[top](#index)