# triton_machine

[back](../triton.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    triton = ">= 0.8.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "triton_machine" {
  source = "./modules/triton/r/triton_machine"

  # administrator_pw - (optional) is a type of string
  administrator_pw = null
  # affinity - (optional) is a type of list of string
  affinity = []
  # cloud_config - (optional) is a type of string
  cloud_config = null
  # delegate_dataset - (optional) is a type of bool
  delegate_dataset = null
  # deletion_protection_enabled - (optional) is a type of bool
  deletion_protection_enabled = null
  # firewall_enabled - (optional) is a type of bool
  firewall_enabled = null
  # image - (required) is a type of string
  image = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (optional) is a type of string
  name = null
  # networks - (optional) is a type of list of string
  networks = []
  # package - (required) is a type of string
  package = null
  # root_authorized_keys - (optional) is a type of string
  root_authorized_keys = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user_data - (optional) is a type of string
  user_data = null
  # user_script - (optional) is a type of string
  user_script = null

  cns = [{
    disable  = null
    services = []
  }]

  locality = [{
    close_to = []
    far_from = []
  }]

  nic = [{
    gateway = null
    ip      = null
    mac     = null
    netmask = null
    network = null
    primary = null
    state   = null
  }]

  timeouts = [{
    create = null
    delete = null
    read   = null
    update = null
  }]

  volume = [{
    mode       = null
    mountpoint = null
    name       = null
    type       = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "administrator_pw" {
  description = "(optional) - Administrator's initial password (Windows only)"
  type        = string
  default     = null
}

variable "affinity" {
  description = "(optional) - Label based affinity rules for assisting instance placement"
  type        = list(string)
  default     = null
}

variable "cloud_config" {
  description = "(optional) - copied to machine on boot"
  type        = string
  default     = null
}

variable "delegate_dataset" {
  description = "(optional) - Whether to create a delegate dataset for this machine"
  type        = bool
  default     = null
}

variable "deletion_protection_enabled" {
  description = "(optional) - Whether to enable deletion protection for this machine"
  type        = bool
  default     = null
}

variable "firewall_enabled" {
  description = "(optional) - Whether to enable the firewall for this machine"
  type        = bool
  default     = null
}

variable "image" {
  description = "(required) - UUID of the image"
  type        = string
}

variable "metadata" {
  description = "(optional) - Machine metadata"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(optional) - Friendly name for machine"
  type        = string
  default     = null
}

variable "networks" {
  description = "(optional) - Desired network IDs"
  type        = list(string)
  default     = null
}

variable "package" {
  description = "(required) - The package for use for provisioning"
  type        = string
}

variable "root_authorized_keys" {
  description = "(optional) - Authorized keys for the root user on this machine"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - Machine tags"
  type        = map(string)
  default     = null
}

variable "user_data" {
  description = "(optional) - Data copied to machine on boot"
  type        = string
  default     = null
}

variable "user_script" {
  description = "(optional) - User script to run on boot (every boot on SmartMachines)"
  type        = string
  default     = null
}

variable "cns" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      disable  = bool
      services = list(string)
    }
  ))
  default = []
}

variable "locality" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      close_to = list(string)
      far_from = list(string)
    }
  ))
  default = []
}

variable "nic" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      gateway = string
      ip      = string
      mac     = string
      netmask = string
      network = string
      primary = bool
      state   = string
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
      read   = string
      update = string
    }
  ))
  default = []
}

variable "volume" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      mode       = string
      mountpoint = string
      name       = string
      type       = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "triton_machine" "this" {
  administrator_pw            = var.administrator_pw
  affinity                    = var.affinity
  cloud_config                = var.cloud_config
  delegate_dataset            = var.delegate_dataset
  deletion_protection_enabled = var.deletion_protection_enabled
  firewall_enabled            = var.firewall_enabled
  image                       = var.image
  metadata                    = var.metadata
  name                        = var.name
  networks                    = var.networks
  package                     = var.package
  root_authorized_keys        = var.root_authorized_keys
  tags                        = var.tags
  user_data                   = var.user_data
  user_script                 = var.user_script

  dynamic "cns" {
    for_each = var.cns
    content {
      disable  = cns.value["disable"]
      services = cns.value["services"]
    }
  }

  dynamic "locality" {
    for_each = var.locality
    content {
      close_to = locality.value["close_to"]
      far_from = locality.value["far_from"]
    }
  }

  dynamic "nic" {
    for_each = var.nic
    content {
      network = nic.value["network"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      read   = timeouts.value["read"]
      update = timeouts.value["update"]
    }
  }

  dynamic "volume" {
    for_each = var.volume
    content {
      mode       = volume.value["mode"]
      mountpoint = volume.value["mountpoint"]
      name       = volume.value["name"]
      type       = volume.value["type"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "compute_node" {
  description = "returns a string"
  value       = triton_machine.this.compute_node
}

output "created" {
  description = "returns a string"
  value       = triton_machine.this.created
}

output "dataset" {
  description = "returns a string"
  value       = triton_machine.this.dataset
}

output "disk" {
  description = "returns a number"
  value       = triton_machine.this.disk
}

output "domain_names" {
  description = "returns a list of string"
  value       = triton_machine.this.domain_names
}

output "id" {
  description = "returns a string"
  value       = triton_machine.this.id
}

output "ips" {
  description = "returns a list of string"
  value       = triton_machine.this.ips
}

output "memory" {
  description = "returns a number"
  value       = triton_machine.this.memory
}

output "name" {
  description = "returns a string"
  value       = triton_machine.this.name
}

output "primaryip" {
  description = "returns a string"
  value       = triton_machine.this.primaryip
}

output "root_authorized_keys" {
  description = "returns a string"
  value       = triton_machine.this.root_authorized_keys
}

output "type" {
  description = "returns a string"
  value       = triton_machine.this.type
}

output "updated" {
  description = "returns a string"
  value       = triton_machine.this.updated
}

output "this" {
  value = triton_machine.this
}
```

[top](#index)