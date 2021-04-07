# ecl_baremetal_server_v2

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
module "ecl_baremetal_server_v2" {
  source = "./modules/ecl/r/ecl_baremetal_server_v2"

  # admin_pass - (optional) is a type of string
  admin_pass = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
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
  # user_data - (optional) is a type of string
  user_data = null

  filesystems = [{
    fs_type     = null
    label       = null
    mount_point = null
  }]

  lvm_volume_groups = [{
    logical_volumes = [{
      lv_label = null
      size     = null
    }]
    physical_volume_partition_labels = []
    vg_label                         = null
  }]

  networks = [{
    fixed_ip = null
    plane    = null
    port     = null
    uuid     = null
  }]

  personality = [{
    contents = null
    path     = null
  }]

  raid_arrays = [{
    disk_hardware_ids = []
    partitions = [{
      lvm             = null
      partition_label = null
      size            = null
    }]
    primary_storage       = null
    raid_card_hardware_id = null
    raid_level            = null
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
variable "admin_pass" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
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

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filesystems" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      fs_type     = string
      label       = string
      mount_point = string
    }
  ))
  default = []
}

variable "lvm_volume_groups" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      logical_volumes = list(object(
        {
          lv_label = string
          size     = string
        }
      ))
      physical_volume_partition_labels = list(string)
      vg_label                         = string
    }
  ))
  default = []
}

variable "networks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      fixed_ip = string
      plane    = string
      port     = string
      uuid     = string
    }
  ))
  default = []
}

variable "personality" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      contents = string
      path     = string
    }
  ))
  default = []
}

variable "raid_arrays" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      disk_hardware_ids = list(string)
      partitions = list(object(
        {
          lvm             = bool
          partition_label = string
          size            = string
        }
      ))
      primary_storage       = bool
      raid_card_hardware_id = string
      raid_level            = number
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
resource "ecl_baremetal_server_v2" "this" {
  # admin_pass - (optional) is a type of string
  admin_pass = var.admin_pass
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # flavor_id - (optional) is a type of string
  flavor_id = var.flavor_id
  # flavor_name - (optional) is a type of string
  flavor_name = var.flavor_name
  # image_id - (optional) is a type of string
  image_id = var.image_id
  # image_name - (optional) is a type of string
  image_name = var.image_name
  # key_pair - (optional) is a type of string
  key_pair = var.key_pair
  # metadata - (optional) is a type of map of string
  metadata = var.metadata
  # name - (required) is a type of string
  name = var.name
  # user_data - (optional) is a type of string
  user_data = var.user_data

  dynamic "filesystems" {
    for_each = var.filesystems
    content {
      # fs_type - (optional) is a type of string
      fs_type = filesystems.value["fs_type"]
      # label - (optional) is a type of string
      label = filesystems.value["label"]
      # mount_point - (optional) is a type of string
      mount_point = filesystems.value["mount_point"]
    }
  }

  dynamic "lvm_volume_groups" {
    for_each = var.lvm_volume_groups
    content {
      # physical_volume_partition_labels - (optional) is a type of list of string
      physical_volume_partition_labels = lvm_volume_groups.value["physical_volume_partition_labels"]
      # vg_label - (optional) is a type of string
      vg_label = lvm_volume_groups.value["vg_label"]

      dynamic "logical_volumes" {
        for_each = lvm_volume_groups.value.logical_volumes
        content {
          # lv_label - (optional) is a type of string
          lv_label = logical_volumes.value["lv_label"]
          # size - (optional) is a type of string
          size = logical_volumes.value["size"]
        }
      }

    }
  }

  dynamic "networks" {
    for_each = var.networks
    content {
      # fixed_ip - (optional) is a type of string
      fixed_ip = networks.value["fixed_ip"]
      # plane - (optional) is a type of string
      plane = networks.value["plane"]
      # port - (optional) is a type of string
      port = networks.value["port"]
      # uuid - (optional) is a type of string
      uuid = networks.value["uuid"]
    }
  }

  dynamic "personality" {
    for_each = var.personality
    content {
      # contents - (optional) is a type of string
      contents = personality.value["contents"]
      # path - (optional) is a type of string
      path = personality.value["path"]
    }
  }

  dynamic "raid_arrays" {
    for_each = var.raid_arrays
    content {
      # disk_hardware_ids - (optional) is a type of list of string
      disk_hardware_ids = raid_arrays.value["disk_hardware_ids"]
      # primary_storage - (optional) is a type of bool
      primary_storage = raid_arrays.value["primary_storage"]
      # raid_card_hardware_id - (optional) is a type of string
      raid_card_hardware_id = raid_arrays.value["raid_card_hardware_id"]
      # raid_level - (optional) is a type of number
      raid_level = raid_arrays.value["raid_level"]

      dynamic "partitions" {
        for_each = raid_arrays.value.partitions
        content {
          # lvm - (optional) is a type of bool
          lvm = partitions.value["lvm"]
          # partition_label - (optional) is a type of string
          partition_label = partitions.value["partition_label"]
          # size - (optional) is a type of string
          size = partitions.value["size"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
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
  value       = ecl_baremetal_server_v2.this.id
}

output "nic_physical_ports" {
  description = "returns a list of object"
  value       = ecl_baremetal_server_v2.this.nic_physical_ports
}

output "this" {
  value = ecl_baremetal_server_v2.this
}
```

[top](#index)