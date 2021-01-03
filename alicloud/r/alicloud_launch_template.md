# alicloud_launch_template

[back](../alicloud.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    alicloud = ">= 1.111.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_launch_template" {
  source = "./modules/alicloud/r/alicloud_launch_template"

  # auto_release_time - (optional) is a type of string
  auto_release_time = null
  # description - (optional) is a type of string
  description = null
  # host_name - (optional) is a type of string
  host_name = null
  # image_id - (optional) is a type of string
  image_id = null
  # image_owner_alias - (optional) is a type of string
  image_owner_alias = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
  # internet_max_bandwidth_in - (optional) is a type of number
  internet_max_bandwidth_in = null
  # internet_max_bandwidth_out - (optional) is a type of number
  internet_max_bandwidth_out = null
  # io_optimized - (optional) is a type of string
  io_optimized = null
  # key_pair_name - (optional) is a type of string
  key_pair_name = null
  # name - (required) is a type of string
  name = null
  # network_type - (optional) is a type of string
  network_type = null
  # ram_role_name - (optional) is a type of string
  ram_role_name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # security_enhancement_strategy - (optional) is a type of string
  security_enhancement_strategy = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # spot_price_limit - (optional) is a type of number
  spot_price_limit = null
  # spot_strategy - (optional) is a type of string
  spot_strategy = null
  # system_disk_category - (optional) is a type of string
  system_disk_category = null
  # system_disk_description - (optional) is a type of string
  system_disk_description = null
  # system_disk_name - (optional) is a type of string
  system_disk_name = null
  # system_disk_size - (optional) is a type of number
  system_disk_size = null
  # tags - (optional) is a type of map of string
  tags = {}
  # userdata - (optional) is a type of string
  userdata = null
  # vpc_id - (optional) is a type of string
  vpc_id = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
  # zone_id - (optional) is a type of string
  zone_id = null

  data_disks = [{
    category             = null
    delete_with_instance = null
    description          = null
    encrypted            = null
    name                 = null
    size                 = null
    snapshot_id          = null
  }]

  network_interfaces = [{
    description       = null
    name              = null
    primary_ip        = null
    security_group_id = null
    vswitch_id        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_release_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "host_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "image_owner_alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "internet_max_bandwidth_in" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "internet_max_bandwidth_out" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "io_optimized" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "key_pair_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "network_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ram_role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_enhancement_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "spot_price_limit" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "spot_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_disk_category" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_disk_description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_disk_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_disk_size" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "userdata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vpc_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_disks" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      category             = string
      delete_with_instance = bool
      description          = string
      encrypted            = bool
      name                 = string
      size                 = number
      snapshot_id          = string
    }
  ))
  default = []
}

variable "network_interfaces" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      description       = string
      name              = string
      primary_ip        = string
      security_group_id = string
      vswitch_id        = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_launch_template" "this" {
  auto_release_time             = var.auto_release_time
  description                   = var.description
  host_name                     = var.host_name
  image_id                      = var.image_id
  image_owner_alias             = var.image_owner_alias
  instance_charge_type          = var.instance_charge_type
  instance_name                 = var.instance_name
  instance_type                 = var.instance_type
  internet_charge_type          = var.internet_charge_type
  internet_max_bandwidth_in     = var.internet_max_bandwidth_in
  internet_max_bandwidth_out    = var.internet_max_bandwidth_out
  io_optimized                  = var.io_optimized
  key_pair_name                 = var.key_pair_name
  name                          = var.name
  network_type                  = var.network_type
  ram_role_name                 = var.ram_role_name
  resource_group_id             = var.resource_group_id
  security_enhancement_strategy = var.security_enhancement_strategy
  security_group_id             = var.security_group_id
  spot_price_limit              = var.spot_price_limit
  spot_strategy                 = var.spot_strategy
  system_disk_category          = var.system_disk_category
  system_disk_description       = var.system_disk_description
  system_disk_name              = var.system_disk_name
  system_disk_size              = var.system_disk_size
  tags                          = var.tags
  userdata                      = var.userdata
  vpc_id                        = var.vpc_id
  vswitch_id                    = var.vswitch_id
  zone_id                       = var.zone_id

  dynamic "data_disks" {
    for_each = var.data_disks
    content {
      category             = data_disks.value["category"]
      delete_with_instance = data_disks.value["delete_with_instance"]
      description          = data_disks.value["description"]
      encrypted            = data_disks.value["encrypted"]
      name                 = data_disks.value["name"]
      size                 = data_disks.value["size"]
      snapshot_id          = data_disks.value["snapshot_id"]
    }
  }

  dynamic "network_interfaces" {
    for_each = var.network_interfaces
    content {
      description       = network_interfaces.value["description"]
      name              = network_interfaces.value["name"]
      primary_ip        = network_interfaces.value["primary_ip"]
      security_group_id = network_interfaces.value["security_group_id"]
      vswitch_id        = network_interfaces.value["vswitch_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_launch_template.this.id
}

output "internet_max_bandwidth_in" {
  description = "returns a number"
  value       = alicloud_launch_template.this.internet_max_bandwidth_in
}

output "this" {
  value = alicloud_launch_template.this
}
```

[top](#index)