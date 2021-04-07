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
    alicloud = ">= 1.120.0"
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
  # deployment_set_id - (optional) is a type of string
  deployment_set_id = null
  # description - (optional) is a type of string
  description = null
  # enable_vm_os_config - (optional) is a type of bool
  enable_vm_os_config = null
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
  # launch_template_name - (optional) is a type of string
  launch_template_name = null
  # name - (optional) is a type of string
  name = null
  # network_type - (optional) is a type of string
  network_type = null
  # password_inherit - (optional) is a type of bool
  password_inherit = null
  # period - (optional) is a type of number
  period = null
  # private_ip_address - (optional) is a type of string
  private_ip_address = null
  # ram_role_name - (optional) is a type of string
  ram_role_name = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # security_enhancement_strategy - (optional) is a type of string
  security_enhancement_strategy = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # security_group_ids - (optional) is a type of list of string
  security_group_ids = []
  # spot_duration - (optional) is a type of string
  spot_duration = null
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
  # template_resource_group_id - (optional) is a type of string
  template_resource_group_id = null
  # template_tags - (optional) is a type of map of string
  template_tags = {}
  # user_data - (optional) is a type of string
  user_data = null
  # userdata - (optional) is a type of string
  userdata = null
  # version_description - (optional) is a type of string
  version_description = null
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
    performance_level    = null
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

  system_disk = [{
    category             = null
    delete_with_instance = null
    description          = null
    iops                 = null
    name                 = null
    performance_level    = null
    size                 = null
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

variable "deployment_set_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_vm_os_config" {
  description = "(optional)"
  type        = bool
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

variable "launch_template_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "network_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password_inherit" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "private_ip_address" {
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

variable "security_group_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "spot_duration" {
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

variable "template_resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "template_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "userdata" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "version_description" {
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
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      category             = string
      delete_with_instance = bool
      description          = string
      encrypted            = bool
      name                 = string
      performance_level    = string
      size                 = number
      snapshot_id          = string
    }
  ))
  default = []
}

variable "network_interfaces" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
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

variable "system_disk" {
  description = "nested block: NestingSet, min items: 0, max items: 1"
  type = set(object(
    {
      category             = string
      delete_with_instance = bool
      description          = string
      iops                 = string
      name                 = string
      performance_level    = string
      size                 = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_launch_template" "this" {
  # auto_release_time - (optional) is a type of string
  auto_release_time = var.auto_release_time
  # deployment_set_id - (optional) is a type of string
  deployment_set_id = var.deployment_set_id
  # description - (optional) is a type of string
  description = var.description
  # enable_vm_os_config - (optional) is a type of bool
  enable_vm_os_config = var.enable_vm_os_config
  # host_name - (optional) is a type of string
  host_name = var.host_name
  # image_id - (optional) is a type of string
  image_id = var.image_id
  # image_owner_alias - (optional) is a type of string
  image_owner_alias = var.image_owner_alias
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = var.instance_charge_type
  # instance_name - (optional) is a type of string
  instance_name = var.instance_name
  # instance_type - (optional) is a type of string
  instance_type = var.instance_type
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = var.internet_charge_type
  # internet_max_bandwidth_in - (optional) is a type of number
  internet_max_bandwidth_in = var.internet_max_bandwidth_in
  # internet_max_bandwidth_out - (optional) is a type of number
  internet_max_bandwidth_out = var.internet_max_bandwidth_out
  # io_optimized - (optional) is a type of string
  io_optimized = var.io_optimized
  # key_pair_name - (optional) is a type of string
  key_pair_name = var.key_pair_name
  # launch_template_name - (optional) is a type of string
  launch_template_name = var.launch_template_name
  # name - (optional) is a type of string
  name = var.name
  # network_type - (optional) is a type of string
  network_type = var.network_type
  # password_inherit - (optional) is a type of bool
  password_inherit = var.password_inherit
  # period - (optional) is a type of number
  period = var.period
  # private_ip_address - (optional) is a type of string
  private_ip_address = var.private_ip_address
  # ram_role_name - (optional) is a type of string
  ram_role_name = var.ram_role_name
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # security_enhancement_strategy - (optional) is a type of string
  security_enhancement_strategy = var.security_enhancement_strategy
  # security_group_id - (optional) is a type of string
  security_group_id = var.security_group_id
  # security_group_ids - (optional) is a type of list of string
  security_group_ids = var.security_group_ids
  # spot_duration - (optional) is a type of string
  spot_duration = var.spot_duration
  # spot_price_limit - (optional) is a type of number
  spot_price_limit = var.spot_price_limit
  # spot_strategy - (optional) is a type of string
  spot_strategy = var.spot_strategy
  # system_disk_category - (optional) is a type of string
  system_disk_category = var.system_disk_category
  # system_disk_description - (optional) is a type of string
  system_disk_description = var.system_disk_description
  # system_disk_name - (optional) is a type of string
  system_disk_name = var.system_disk_name
  # system_disk_size - (optional) is a type of number
  system_disk_size = var.system_disk_size
  # tags - (optional) is a type of map of string
  tags = var.tags
  # template_resource_group_id - (optional) is a type of string
  template_resource_group_id = var.template_resource_group_id
  # template_tags - (optional) is a type of map of string
  template_tags = var.template_tags
  # user_data - (optional) is a type of string
  user_data = var.user_data
  # userdata - (optional) is a type of string
  userdata = var.userdata
  # version_description - (optional) is a type of string
  version_description = var.version_description
  # vpc_id - (optional) is a type of string
  vpc_id = var.vpc_id
  # vswitch_id - (optional) is a type of string
  vswitch_id = var.vswitch_id
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id

  dynamic "data_disks" {
    for_each = var.data_disks
    content {
      # category - (optional) is a type of string
      category = data_disks.value["category"]
      # delete_with_instance - (optional) is a type of bool
      delete_with_instance = data_disks.value["delete_with_instance"]
      # description - (optional) is a type of string
      description = data_disks.value["description"]
      # encrypted - (optional) is a type of bool
      encrypted = data_disks.value["encrypted"]
      # name - (optional) is a type of string
      name = data_disks.value["name"]
      # performance_level - (optional) is a type of string
      performance_level = data_disks.value["performance_level"]
      # size - (optional) is a type of number
      size = data_disks.value["size"]
      # snapshot_id - (optional) is a type of string
      snapshot_id = data_disks.value["snapshot_id"]
    }
  }

  dynamic "network_interfaces" {
    for_each = var.network_interfaces
    content {
      # description - (optional) is a type of string
      description = network_interfaces.value["description"]
      # name - (optional) is a type of string
      name = network_interfaces.value["name"]
      # primary_ip - (optional) is a type of string
      primary_ip = network_interfaces.value["primary_ip"]
      # security_group_id - (optional) is a type of string
      security_group_id = network_interfaces.value["security_group_id"]
      # vswitch_id - (optional) is a type of string
      vswitch_id = network_interfaces.value["vswitch_id"]
    }
  }

  dynamic "system_disk" {
    for_each = var.system_disk
    content {
      # category - (optional) is a type of string
      category = system_disk.value["category"]
      # delete_with_instance - (optional) is a type of bool
      delete_with_instance = system_disk.value["delete_with_instance"]
      # description - (optional) is a type of string
      description = system_disk.value["description"]
      # iops - (optional) is a type of string
      iops = system_disk.value["iops"]
      # name - (optional) is a type of string
      name = system_disk.value["name"]
      # performance_level - (optional) is a type of string
      performance_level = system_disk.value["performance_level"]
      # size - (optional) is a type of number
      size = system_disk.value["size"]
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

output "launch_template_name" {
  description = "returns a string"
  value       = alicloud_launch_template.this.launch_template_name
}

output "name" {
  description = "returns a string"
  value       = alicloud_launch_template.this.name
}

output "system_disk_category" {
  description = "returns a string"
  value       = alicloud_launch_template.this.system_disk_category
}

output "system_disk_description" {
  description = "returns a string"
  value       = alicloud_launch_template.this.system_disk_description
}

output "system_disk_name" {
  description = "returns a string"
  value       = alicloud_launch_template.this.system_disk_name
}

output "system_disk_size" {
  description = "returns a number"
  value       = alicloud_launch_template.this.system_disk_size
}

output "user_data" {
  description = "returns a string"
  value       = alicloud_launch_template.this.user_data
}

output "userdata" {
  description = "returns a string"
  value       = alicloud_launch_template.this.userdata
}

output "this" {
  value = alicloud_launch_template.this
}
```

[top](#index)