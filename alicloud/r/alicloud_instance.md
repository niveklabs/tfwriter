# alicloud_instance

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
module "alicloud_instance" {
  source = "./modules/alicloud/r/alicloud_instance"

  # allocate_public_ip - (optional) is a type of bool
  allocate_public_ip = null
  # auto_release_time - (optional) is a type of string
  auto_release_time = null
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # credit_specification - (optional) is a type of string
  credit_specification = null
  # deletion_protection - (optional) is a type of bool
  deletion_protection = null
  # description - (optional) is a type of string
  description = null
  # dry_run - (optional) is a type of bool
  dry_run = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # host_name - (optional) is a type of string
  host_name = null
  # image_id - (required) is a type of string
  image_id = null
  # include_data_disks - (optional) is a type of bool
  include_data_disks = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # instance_type - (required) is a type of string
  instance_type = null
  # internet_charge_type - (optional) is a type of string
  internet_charge_type = null
  # internet_max_bandwidth_in - (optional) is a type of number
  internet_max_bandwidth_in = null
  # internet_max_bandwidth_out - (optional) is a type of number
  internet_max_bandwidth_out = null
  # io_optimized - (optional) is a type of string
  io_optimized = null
  # is_outdated - (optional) is a type of bool
  is_outdated = null
  # key_name - (optional) is a type of string
  key_name = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}
  # password - (optional) is a type of string
  password = null
  # period - (optional) is a type of number
  period = null
  # period_unit - (optional) is a type of string
  period_unit = null
  # private_ip - (optional) is a type of string
  private_ip = null
  # renewal_status - (optional) is a type of string
  renewal_status = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # role_name - (optional) is a type of string
  role_name = null
  # security_enhancement_strategy - (optional) is a type of string
  security_enhancement_strategy = null
  # security_groups - (required) is a type of set of string
  security_groups = []
  # spot_price_limit - (optional) is a type of number
  spot_price_limit = null
  # spot_strategy - (optional) is a type of string
  spot_strategy = null
  # status - (optional) is a type of string
  status = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # system_disk_auto_snapshot_policy_id - (optional) is a type of string
  system_disk_auto_snapshot_policy_id = null
  # system_disk_category - (optional) is a type of string
  system_disk_category = null
  # system_disk_description - (optional) is a type of string
  system_disk_description = null
  # system_disk_name - (optional) is a type of string
  system_disk_name = null
  # system_disk_performance_level - (optional) is a type of string
  system_disk_performance_level = null
  # system_disk_size - (optional) is a type of number
  system_disk_size = null
  # tags - (optional) is a type of map of string
  tags = {}
  # user_data - (optional) is a type of string
  user_data = null
  # volume_tags - (optional) is a type of map of string
  volume_tags = {}
  # vswitch_id - (optional) is a type of string
  vswitch_id = null

  data_disks = [{
    auto_snapshot_policy_id = null
    category                = null
    delete_with_instance    = null
    description             = null
    encrypted               = null
    kms_key_id              = null
    name                    = null
    performance_level       = null
    size                    = null
    snapshot_id             = null
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
variable "allocate_public_ip" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_release_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auto_renew_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "credit_specification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deletion_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dry_run" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "force_delete" {
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
  description = "(required)"
  type        = string
}

variable "include_data_disks" {
  description = "(optional)"
  type        = bool
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
  description = "(required)"
  type        = string
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

variable "is_outdated" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "key_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_encrypted_password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "kms_encryption_context" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "period_unit" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "renewal_status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_enhancement_strategy" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_groups" {
  description = "(required)"
  type        = set(string)
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

variable "status" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "system_disk_auto_snapshot_policy_id" {
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

variable "system_disk_performance_level" {
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

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "volume_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "data_disks" {
  description = "nested block: NestingList, min items: 0, max items: 16"
  type = set(object(
    {
      auto_snapshot_policy_id = string
      category                = string
      delete_with_instance    = bool
      description             = string
      encrypted               = bool
      kms_key_id              = string
      name                    = string
      performance_level       = string
      size                    = number
      snapshot_id             = string
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
resource "alicloud_instance" "this" {
  allocate_public_ip                  = var.allocate_public_ip
  auto_release_time                   = var.auto_release_time
  auto_renew_period                   = var.auto_renew_period
  availability_zone                   = var.availability_zone
  credit_specification                = var.credit_specification
  deletion_protection                 = var.deletion_protection
  description                         = var.description
  dry_run                             = var.dry_run
  force_delete                        = var.force_delete
  host_name                           = var.host_name
  image_id                            = var.image_id
  include_data_disks                  = var.include_data_disks
  instance_charge_type                = var.instance_charge_type
  instance_name                       = var.instance_name
  instance_type                       = var.instance_type
  internet_charge_type                = var.internet_charge_type
  internet_max_bandwidth_in           = var.internet_max_bandwidth_in
  internet_max_bandwidth_out          = var.internet_max_bandwidth_out
  io_optimized                        = var.io_optimized
  is_outdated                         = var.is_outdated
  key_name                            = var.key_name
  kms_encrypted_password              = var.kms_encrypted_password
  kms_encryption_context              = var.kms_encryption_context
  password                            = var.password
  period                              = var.period
  period_unit                         = var.period_unit
  private_ip                          = var.private_ip
  renewal_status                      = var.renewal_status
  resource_group_id                   = var.resource_group_id
  role_name                           = var.role_name
  security_enhancement_strategy       = var.security_enhancement_strategy
  security_groups                     = var.security_groups
  spot_price_limit                    = var.spot_price_limit
  spot_strategy                       = var.spot_strategy
  status                              = var.status
  subnet_id                           = var.subnet_id
  system_disk_auto_snapshot_policy_id = var.system_disk_auto_snapshot_policy_id
  system_disk_category                = var.system_disk_category
  system_disk_description             = var.system_disk_description
  system_disk_name                    = var.system_disk_name
  system_disk_performance_level       = var.system_disk_performance_level
  system_disk_size                    = var.system_disk_size
  tags                                = var.tags
  user_data                           = var.user_data
  volume_tags                         = var.volume_tags
  vswitch_id                          = var.vswitch_id

  dynamic "data_disks" {
    for_each = var.data_disks
    content {
      auto_snapshot_policy_id = data_disks.value["auto_snapshot_policy_id"]
      category                = data_disks.value["category"]
      delete_with_instance    = data_disks.value["delete_with_instance"]
      description             = data_disks.value["description"]
      encrypted               = data_disks.value["encrypted"]
      kms_key_id              = data_disks.value["kms_key_id"]
      name                    = data_disks.value["name"]
      performance_level       = data_disks.value["performance_level"]
      size                    = data_disks.value["size"]
      snapshot_id             = data_disks.value["snapshot_id"]
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
output "availability_zone" {
  description = "returns a string"
  value       = alicloud_instance.this.availability_zone
}

output "credit_specification" {
  description = "returns a string"
  value       = alicloud_instance.this.credit_specification
}

output "host_name" {
  description = "returns a string"
  value       = alicloud_instance.this.host_name
}

output "id" {
  description = "returns a string"
  value       = alicloud_instance.this.id
}

output "internet_max_bandwidth_in" {
  description = "returns a number"
  value       = alicloud_instance.this.internet_max_bandwidth_in
}

output "key_name" {
  description = "returns a string"
  value       = alicloud_instance.this.key_name
}

output "private_ip" {
  description = "returns a string"
  value       = alicloud_instance.this.private_ip
}

output "public_ip" {
  description = "returns a string"
  value       = alicloud_instance.this.public_ip
}

output "role_name" {
  description = "returns a string"
  value       = alicloud_instance.this.role_name
}

output "subnet_id" {
  description = "returns a string"
  value       = alicloud_instance.this.subnet_id
}

output "system_disk_performance_level" {
  description = "returns a string"
  value       = alicloud_instance.this.system_disk_performance_level
}

output "volume_tags" {
  description = "returns a map of string"
  value       = alicloud_instance.this.volume_tags
}

output "this" {
  value = alicloud_instance.this
}
```

[top](#index)