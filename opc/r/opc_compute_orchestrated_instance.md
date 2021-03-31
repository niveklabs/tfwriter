# opc_compute_orchestrated_instance

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_orchestrated_instance" {
  source = "./modules/opc/r/opc_compute_orchestrated_instance"

  # description - (optional) is a type of string
  description = null
  # desired_state - (required) is a type of string
  desired_state = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of list of string
  tags = []

  instance = [{
    attributes          = null
    availability_domain = null
    boot_order          = []
    domain              = null
    entry               = null
    fingerprint         = null
    fqdn                = null
    hostname            = null
    id                  = null
    image_format        = null
    image_list          = null
    instance_attributes = null
    ip_address          = null
    label               = null
    name                = null
    networking_info = [{
      dns                = []
      index              = null
      ip_address         = null
      ip_network         = null
      is_default_gateway = null
      mac_address        = null
      name_servers       = []
      nat                = []
      search_domains     = []
      sec_lists          = []
      shared_network     = null
      vnic               = null
      vnic_sets          = []
    }]
    persistent             = null
    placement_requirements = []
    platform               = null
    priority               = null
    quota_reservation      = null
    relationships          = []
    resolvers              = []
    reverse_dns            = null
    shape                  = null
    site                   = null
    ssh_keys               = []
    start_time             = null
    state                  = null
    storage = [{
      index  = null
      name   = null
      volume = null
    }]
    tags        = []
    vcable      = null
    virtio      = null
    vnc_address = null
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
variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "desired_state" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "instance" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      attributes          = string
      availability_domain = string
      boot_order          = list(number)
      domain              = string
      entry               = number
      fingerprint         = string
      fqdn                = string
      hostname            = string
      id                  = string
      image_format        = string
      image_list          = string
      instance_attributes = string
      ip_address          = string
      label               = string
      name                = string
      networking_info = list(object(
        {
          dns                = list(string)
          index              = number
          ip_address         = string
          ip_network         = string
          is_default_gateway = bool
          mac_address        = string
          name_servers       = list(string)
          nat                = list(string)
          search_domains     = list(string)
          sec_lists          = list(string)
          shared_network     = bool
          vnic               = string
          vnic_sets          = list(string)
        }
      ))
      persistent             = bool
      placement_requirements = list(string)
      platform               = string
      priority               = string
      quota_reservation      = string
      relationships          = list(string)
      resolvers              = list(string)
      reverse_dns            = bool
      shape                  = string
      site                   = string
      ssh_keys               = list(string)
      start_time             = string
      state                  = string
      storage = list(object(
        {
          index  = number
          name   = string
          volume = string
        }
      ))
      tags        = list(string)
      vcable      = string
      virtio      = bool
      vnc_address = string
    }
  ))
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
resource "opc_compute_orchestrated_instance" "this" {
  description   = var.description
  desired_state = var.desired_state
  name          = var.name
  tags          = var.tags

  dynamic "instance" {
    for_each = var.instance
    content {
      boot_order          = instance.value["boot_order"]
      hostname            = instance.value["hostname"]
      image_list          = instance.value["image_list"]
      instance_attributes = instance.value["instance_attributes"]
      label               = instance.value["label"]
      name                = instance.value["name"]
      persistent          = instance.value["persistent"]
      reverse_dns         = instance.value["reverse_dns"]
      shape               = instance.value["shape"]
      ssh_keys            = instance.value["ssh_keys"]
      tags                = instance.value["tags"]

      dynamic "networking_info" {
        for_each = instance.value.networking_info
        content {
          dns                = networking_info.value["dns"]
          index              = networking_info.value["index"]
          ip_address         = networking_info.value["ip_address"]
          ip_network         = networking_info.value["ip_network"]
          is_default_gateway = networking_info.value["is_default_gateway"]
          mac_address        = networking_info.value["mac_address"]
          name_servers       = networking_info.value["name_servers"]
          nat                = networking_info.value["nat"]
          search_domains     = networking_info.value["search_domains"]
          sec_lists          = networking_info.value["sec_lists"]
          shared_network     = networking_info.value["shared_network"]
          vnic               = networking_info.value["vnic"]
          vnic_sets          = networking_info.value["vnic_sets"]
        }
      }

      dynamic "storage" {
        for_each = instance.value.storage
        content {
          index  = storage.value["index"]
          volume = storage.value["volume"]
        }
      }

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
output "id" {
  description = "returns a string"
  value       = opc_compute_orchestrated_instance.this.id
}

output "version" {
  description = "returns a number"
  value       = opc_compute_orchestrated_instance.this.version
}

output "this" {
  value = opc_compute_orchestrated_instance.this
}
```

[top](#index)