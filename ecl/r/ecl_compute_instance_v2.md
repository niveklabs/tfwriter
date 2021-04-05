# ecl_compute_instance_v2

[back](../ecl.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ecl = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ecl_compute_instance_v2" {
  source = "./modules/ecl/r/ecl_compute_instance_v2"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # config_drive - (optional) is a type of bool
  config_drive = null
  # flavor_id - (optional) is a type of string
  flavor_id = null
  # flavor_name - (optional) is a type of string
  flavor_name = null
  # image_id - (optional) is a type of string
  image_id = null
  # image_name - (optional) is a type of string
  image_name = null
  # key_pair - (optional) is a type of string
  key_pair = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # name - (required) is a type of string
  name = null
  # power_state - (optional) is a type of string
  power_state = null
  # region - (optional) is a type of string
  region = null
  # stop_before_destroy - (optional) is a type of bool
  stop_before_destroy = null
  # user_data - (optional) is a type of string
  user_data = null

  block_device = [{
    boot_index            = null
    delete_on_termination = null
    destination_type      = null
    source_type           = null
    uuid                  = null
    volume_size           = null
  }]

  network = [{
    access_network = null
    fixed_ip_v4    = null
    mac            = null
    name           = null
    port           = null
    uuid           = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  volume = [{
    device    = null
    id        = null
    volume_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "config_drive" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "flavor_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "flavor_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_pair" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "power_state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "region" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "stop_before_destroy" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "block_device" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      boot_index            = number
      delete_on_termination = bool
      destination_type      = string
      source_type           = string
      uuid                  = string
      volume_size           = number
    }
  ))
  default = []
}

variable "network" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      access_network = bool
      fixed_ip_v4    = string
      mac            = string
      name           = string
      port           = string
      uuid           = string
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

variable "volume" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      device    = string
      id        = string
      volume_id = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "ecl_compute_instance_v2" "this" {
  availability_zone   = var.availability_zone
  config_drive        = var.config_drive
  flavor_id           = var.flavor_id
  flavor_name         = var.flavor_name
  image_id            = var.image_id
  image_name          = var.image_name
  key_pair            = var.key_pair
  metadata            = var.metadata
  name                = var.name
  power_state         = var.power_state
  region              = var.region
  stop_before_destroy = var.stop_before_destroy
  user_data           = var.user_data

  dynamic "block_device" {
    for_each = var.block_device
    content {
      boot_index            = block_device.value["boot_index"]
      delete_on_termination = block_device.value["delete_on_termination"]
      destination_type      = block_device.value["destination_type"]
      source_type           = block_device.value["source_type"]
      uuid                  = block_device.value["uuid"]
      volume_size           = block_device.value["volume_size"]
    }
  }

  dynamic "network" {
    for_each = var.network
    content {
      access_network = network.value["access_network"]
      fixed_ip_v4    = network.value["fixed_ip_v4"]
      name           = network.value["name"]
      port           = network.value["port"]
      uuid           = network.value["uuid"]
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

  dynamic "volume" {
    for_each = var.volume
    content {
      device    = volume.value["device"]
      id        = volume.value["id"]
      volume_id = volume.value["volume_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "access_ip_v4" {
  description = "returns a string"
  value       = ecl_compute_instance_v2.this.access_ip_v4
}

output "all_metadata" {
  description = "returns a map of string"
  value       = ecl_compute_instance_v2.this.all_metadata
}

output "availability_zone" {
  description = "returns a string"
  value       = ecl_compute_instance_v2.this.availability_zone
}

output "flavor_id" {
  description = "returns a string"
  value       = ecl_compute_instance_v2.this.flavor_id
}

output "flavor_name" {
  description = "returns a string"
  value       = ecl_compute_instance_v2.this.flavor_name
}

output "id" {
  description = "returns a string"
  value       = ecl_compute_instance_v2.this.id
}

output "image_id" {
  description = "returns a string"
  value       = ecl_compute_instance_v2.this.image_id
}

output "image_name" {
  description = "returns a string"
  value       = ecl_compute_instance_v2.this.image_name
}

output "region" {
  description = "returns a string"
  value       = ecl_compute_instance_v2.this.region
}

output "this" {
  value = ecl_compute_instance_v2.this
}
```

[top](#index)