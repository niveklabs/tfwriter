# opc_compute_instance

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
    opc = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_instance" {
  source = "./modules/opc/r/opc_compute_instance"

  # boot_order - (optional) is a type of list of number
  boot_order = []
  # desired_state - (optional) is a type of string
  desired_state = null
  # hostname - (optional) is a type of string
  hostname = null
  # image_list - (optional) is a type of string
  image_list = null
  # instance_attributes - (optional) is a type of string
  instance_attributes = null
  # label - (optional) is a type of string
  label = null
  # name - (required) is a type of string
  name = null
  # reverse_dns - (optional) is a type of bool
  reverse_dns = null
  # shape - (required) is a type of string
  shape = null
  # ssh_keys - (optional) is a type of list of string
  ssh_keys = []
  # tags - (optional) is a type of list of string
  tags = []

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

  storage = [{
    index  = null
    name   = null
    volume = null
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
variable "boot_order" {
  description = "(optional)"
  type        = list(number)
  default     = null
}

variable "desired_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_list" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_attributes" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "reverse_dns" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "shape" {
  description = "(required)"
  type        = string
}

variable "ssh_keys" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "networking_info" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
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
  default = []
}

variable "storage" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      index  = number
      name   = string
      volume = string
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
resource "opc_compute_instance" "this" {
  boot_order          = var.boot_order
  desired_state       = var.desired_state
  hostname            = var.hostname
  image_list          = var.image_list
  instance_attributes = var.instance_attributes
  label               = var.label
  name                = var.name
  reverse_dns         = var.reverse_dns
  shape               = var.shape
  ssh_keys            = var.ssh_keys
  tags                = var.tags

  dynamic "networking_info" {
    for_each = var.networking_info
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
    for_each = var.storage
    content {
      index  = storage.value["index"]
      volume = storage.value["volume"]
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
output "attributes" {
  description = "returns a string"
  value       = opc_compute_instance.this.attributes
}

output "availability_domain" {
  description = "returns a string"
  value       = opc_compute_instance.this.availability_domain
}

output "domain" {
  description = "returns a string"
  value       = opc_compute_instance.this.domain
}

output "entry" {
  description = "returns a number"
  value       = opc_compute_instance.this.entry
}

output "fingerprint" {
  description = "returns a string"
  value       = opc_compute_instance.this.fingerprint
}

output "fqdn" {
  description = "returns a string"
  value       = opc_compute_instance.this.fqdn
}

output "hostname" {
  description = "returns a string"
  value       = opc_compute_instance.this.hostname
}

output "id" {
  description = "returns a string"
  value       = opc_compute_instance.this.id
}

output "image_format" {
  description = "returns a string"
  value       = opc_compute_instance.this.image_format
}

output "ip_address" {
  description = "returns a string"
  value       = opc_compute_instance.this.ip_address
}

output "label" {
  description = "returns a string"
  value       = opc_compute_instance.this.label
}

output "placement_requirements" {
  description = "returns a list of string"
  value       = opc_compute_instance.this.placement_requirements
}

output "platform" {
  description = "returns a string"
  value       = opc_compute_instance.this.platform
}

output "priority" {
  description = "returns a string"
  value       = opc_compute_instance.this.priority
}

output "quota_reservation" {
  description = "returns a string"
  value       = opc_compute_instance.this.quota_reservation
}

output "relationships" {
  description = "returns a list of string"
  value       = opc_compute_instance.this.relationships
}

output "resolvers" {
  description = "returns a list of string"
  value       = opc_compute_instance.this.resolvers
}

output "site" {
  description = "returns a string"
  value       = opc_compute_instance.this.site
}

output "start_time" {
  description = "returns a string"
  value       = opc_compute_instance.this.start_time
}

output "state" {
  description = "returns a string"
  value       = opc_compute_instance.this.state
}

output "vcable" {
  description = "returns a string"
  value       = opc_compute_instance.this.vcable
}

output "virtio" {
  description = "returns a bool"
  value       = opc_compute_instance.this.virtio
}

output "vnc_address" {
  description = "returns a string"
  value       = opc_compute_instance.this.vnc_address
}

output "this" {
  value = opc_compute_instance.this
}
```

[top](#index)