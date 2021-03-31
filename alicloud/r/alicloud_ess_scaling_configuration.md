# alicloud_ess_scaling_configuration

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
    alicloud = ">= 1.119.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "alicloud_ess_scaling_configuration" {
  source = "./modules/alicloud/r/alicloud_ess_scaling_configuration"

  # active - (optional) is a type of bool
  active = null
  # credit_specification - (optional) is a type of string
  credit_specification = null
  # enable - (optional) is a type of bool
  enable = null
  # force_delete - (optional) is a type of bool
  force_delete = null
  # image_id - (optional) is a type of string
  image_id = null
  # image_name - (optional) is a type of string
  image_name = null
  # instance_ids - (optional) is a type of list of string
  instance_ids = []
  # instance_name - (optional) is a type of string
  instance_name = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # instance_types - (optional) is a type of list of string
  instance_types = []
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
  # override - (optional) is a type of bool
  override = null
  # password - (optional) is a type of string
  password = null
  # password_inherit - (optional) is a type of bool
  password_inherit = null
  # role_name - (optional) is a type of string
  role_name = null
  # scaling_configuration_name - (optional) is a type of string
  scaling_configuration_name = null
  # scaling_group_id - (required) is a type of string
  scaling_group_id = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # security_group_ids - (optional) is a type of list of string
  security_group_ids = []
  # substitute - (optional) is a type of string
  substitute = null
  # system_disk_auto_snapshot_policy_id - (optional) is a type of string
  system_disk_auto_snapshot_policy_id = null
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
  # user_data - (optional) is a type of string
  user_data = null

  data_disk = [{
    auto_snapshot_policy_id = null
    category                = null
    delete_with_instance    = null
    description             = null
    device                  = null
    encrypted               = null
    kms_key_id              = null
    name                    = null
    size                    = null
    snapshot_id             = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "active" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "credit_specification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "force_delete" {
  description = "(optional)"
  type        = bool
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

variable "instance_ids" {
  description = "(optional)"
  type        = list(string)
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

variable "instance_types" {
  description = "(optional)"
  type        = list(string)
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

variable "override" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password_inherit" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "role_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scaling_configuration_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "scaling_group_id" {
  description = "(required)"
  type        = string
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

variable "substitute" {
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

variable "data_disk" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      auto_snapshot_policy_id = string
      category                = string
      delete_with_instance    = bool
      description             = string
      device                  = string
      encrypted               = bool
      kms_key_id              = string
      name                    = string
      size                    = number
      snapshot_id             = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_ess_scaling_configuration" "this" {
  active                              = var.active
  credit_specification                = var.credit_specification
  enable                              = var.enable
  force_delete                        = var.force_delete
  image_id                            = var.image_id
  image_name                          = var.image_name
  instance_ids                        = var.instance_ids
  instance_name                       = var.instance_name
  instance_type                       = var.instance_type
  instance_types                      = var.instance_types
  internet_charge_type                = var.internet_charge_type
  internet_max_bandwidth_in           = var.internet_max_bandwidth_in
  internet_max_bandwidth_out          = var.internet_max_bandwidth_out
  io_optimized                        = var.io_optimized
  is_outdated                         = var.is_outdated
  key_name                            = var.key_name
  kms_encrypted_password              = var.kms_encrypted_password
  kms_encryption_context              = var.kms_encryption_context
  override                            = var.override
  password                            = var.password
  password_inherit                    = var.password_inherit
  role_name                           = var.role_name
  scaling_configuration_name          = var.scaling_configuration_name
  scaling_group_id                    = var.scaling_group_id
  security_group_id                   = var.security_group_id
  security_group_ids                  = var.security_group_ids
  substitute                          = var.substitute
  system_disk_auto_snapshot_policy_id = var.system_disk_auto_snapshot_policy_id
  system_disk_category                = var.system_disk_category
  system_disk_description             = var.system_disk_description
  system_disk_name                    = var.system_disk_name
  system_disk_size                    = var.system_disk_size
  tags                                = var.tags
  user_data                           = var.user_data

  dynamic "data_disk" {
    for_each = var.data_disk
    content {
      auto_snapshot_policy_id = data_disk.value["auto_snapshot_policy_id"]
      category                = data_disk.value["category"]
      delete_with_instance    = data_disk.value["delete_with_instance"]
      description             = data_disk.value["description"]
      device                  = data_disk.value["device"]
      encrypted               = data_disk.value["encrypted"]
      kms_key_id              = data_disk.value["kms_key_id"]
      name                    = data_disk.value["name"]
      size                    = data_disk.value["size"]
      snapshot_id             = data_disk.value["snapshot_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "active" {
  description = "returns a bool"
  value       = alicloud_ess_scaling_configuration.this.active
}

output "id" {
  description = "returns a string"
  value       = alicloud_ess_scaling_configuration.this.id
}

output "internet_max_bandwidth_in" {
  description = "returns a number"
  value       = alicloud_ess_scaling_configuration.this.internet_max_bandwidth_in
}

output "scaling_configuration_name" {
  description = "returns a string"
  value       = alicloud_ess_scaling_configuration.this.scaling_configuration_name
}

output "substitute" {
  description = "returns a string"
  value       = alicloud_ess_scaling_configuration.this.substitute
}

output "this" {
  value = alicloud_ess_scaling_configuration.this
}
```

[top](#index)