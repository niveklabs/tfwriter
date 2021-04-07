# alicloud_kvstore_instance

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
module "alicloud_kvstore_instance" {
  source = "./modules/alicloud/r/alicloud_kvstore_instance"

  # auto_renew - (optional) is a type of bool
  auto_renew = null
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = null
  # auto_use_coupon - (optional) is a type of bool
  auto_use_coupon = null
  # availability_zone - (optional) is a type of string
  availability_zone = null
  # backup_id - (optional) is a type of string
  backup_id = null
  # backup_period - (optional) is a type of set of string
  backup_period = []
  # backup_time - (optional) is a type of string
  backup_time = null
  # business_info - (optional) is a type of string
  business_info = null
  # capacity - (optional) is a type of number
  capacity = null
  # config - (optional) is a type of map of string
  config = {}
  # connection_string_prefix - (optional) is a type of string
  connection_string_prefix = null
  # coupon_no - (optional) is a type of string
  coupon_no = null
  # db_instance_name - (optional) is a type of string
  db_instance_name = null
  # dedicated_host_group_id - (optional) is a type of string
  dedicated_host_group_id = null
  # enable_backup_log - (optional) is a type of number
  enable_backup_log = null
  # enable_public - (optional) is a type of bool
  enable_public = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # force_upgrade - (optional) is a type of bool
  force_upgrade = null
  # global_instance - (optional) is a type of bool
  global_instance = null
  # global_instance_id - (optional) is a type of string
  global_instance_id = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # instance_class - (optional) is a type of string
  instance_class = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # instance_release_protection - (optional) is a type of bool
  instance_release_protection = null
  # instance_type - (optional) is a type of string
  instance_type = null
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = null
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = {}
  # maintain_end_time - (optional) is a type of string
  maintain_end_time = null
  # maintain_start_time - (optional) is a type of string
  maintain_start_time = null
  # modify_mode - (optional) is a type of number
  modify_mode = null
  # node_type - (optional) is a type of string
  node_type = null
  # order_type - (optional) is a type of string
  order_type = null
  # password - (optional) is a type of string
  password = null
  # payment_type - (optional) is a type of string
  payment_type = null
  # period - (optional) is a type of string
  period = null
  # port - (optional) is a type of number
  port = null
  # private_connection_prefix - (optional) is a type of string
  private_connection_prefix = null
  # private_ip - (optional) is a type of string
  private_ip = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # restore_time - (optional) is a type of string
  restore_time = null
  # security_group_id - (optional) is a type of string
  security_group_id = null
  # security_ip_group_attribute - (optional) is a type of string
  security_ip_group_attribute = null
  # security_ip_group_name - (optional) is a type of string
  security_ip_group_name = null
  # security_ips - (optional) is a type of set of string
  security_ips = []
  # srcdb_instance_id - (optional) is a type of string
  srcdb_instance_id = null
  # ssl_enable - (optional) is a type of string
  ssl_enable = null
  # tags - (optional) is a type of map of string
  tags = {}
  # vpc_auth_mode - (optional) is a type of string
  vpc_auth_mode = null
  # vswitch_id - (optional) is a type of string
  vswitch_id = null
  # zone_id - (optional) is a type of string
  zone_id = null

  parameters = [{
    name  = null
    value = null
  }]

  timeouts = [{
    create = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "auto_renew" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "auto_renew_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "auto_use_coupon" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "availability_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "backup_period" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "backup_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "business_info" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "config" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "connection_string_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "coupon_no" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_instance_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dedicated_host_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enable_backup_log" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "enable_public" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "engine_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "force_upgrade" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "global_instance" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "global_instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_charge_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_class" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_release_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "instance_type" {
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

variable "maintain_end_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maintain_start_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "modify_mode" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "node_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "order_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "payment_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "period" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "private_connection_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "private_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "restore_time" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_ip_group_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_ip_group_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "security_ips" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "srcdb_instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_enable" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vpc_auth_mode" {
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

variable "parameters" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      value = string
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_kvstore_instance" "this" {
  # auto_renew - (optional) is a type of bool
  auto_renew = var.auto_renew
  # auto_renew_period - (optional) is a type of number
  auto_renew_period = var.auto_renew_period
  # auto_use_coupon - (optional) is a type of bool
  auto_use_coupon = var.auto_use_coupon
  # availability_zone - (optional) is a type of string
  availability_zone = var.availability_zone
  # backup_id - (optional) is a type of string
  backup_id = var.backup_id
  # backup_period - (optional) is a type of set of string
  backup_period = var.backup_period
  # backup_time - (optional) is a type of string
  backup_time = var.backup_time
  # business_info - (optional) is a type of string
  business_info = var.business_info
  # capacity - (optional) is a type of number
  capacity = var.capacity
  # config - (optional) is a type of map of string
  config = var.config
  # connection_string_prefix - (optional) is a type of string
  connection_string_prefix = var.connection_string_prefix
  # coupon_no - (optional) is a type of string
  coupon_no = var.coupon_no
  # db_instance_name - (optional) is a type of string
  db_instance_name = var.db_instance_name
  # dedicated_host_group_id - (optional) is a type of string
  dedicated_host_group_id = var.dedicated_host_group_id
  # enable_backup_log - (optional) is a type of number
  enable_backup_log = var.enable_backup_log
  # enable_public - (optional) is a type of bool
  enable_public = var.enable_public
  # engine_version - (optional) is a type of string
  engine_version = var.engine_version
  # force_upgrade - (optional) is a type of bool
  force_upgrade = var.force_upgrade
  # global_instance - (optional) is a type of bool
  global_instance = var.global_instance
  # global_instance_id - (optional) is a type of string
  global_instance_id = var.global_instance_id
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = var.instance_charge_type
  # instance_class - (optional) is a type of string
  instance_class = var.instance_class
  # instance_name - (optional) is a type of string
  instance_name = var.instance_name
  # instance_release_protection - (optional) is a type of bool
  instance_release_protection = var.instance_release_protection
  # instance_type - (optional) is a type of string
  instance_type = var.instance_type
  # kms_encrypted_password - (optional) is a type of string
  kms_encrypted_password = var.kms_encrypted_password
  # kms_encryption_context - (optional) is a type of map of string
  kms_encryption_context = var.kms_encryption_context
  # maintain_end_time - (optional) is a type of string
  maintain_end_time = var.maintain_end_time
  # maintain_start_time - (optional) is a type of string
  maintain_start_time = var.maintain_start_time
  # modify_mode - (optional) is a type of number
  modify_mode = var.modify_mode
  # node_type - (optional) is a type of string
  node_type = var.node_type
  # order_type - (optional) is a type of string
  order_type = var.order_type
  # password - (optional) is a type of string
  password = var.password
  # payment_type - (optional) is a type of string
  payment_type = var.payment_type
  # period - (optional) is a type of string
  period = var.period
  # port - (optional) is a type of number
  port = var.port
  # private_connection_prefix - (optional) is a type of string
  private_connection_prefix = var.private_connection_prefix
  # private_ip - (optional) is a type of string
  private_ip = var.private_ip
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # restore_time - (optional) is a type of string
  restore_time = var.restore_time
  # security_group_id - (optional) is a type of string
  security_group_id = var.security_group_id
  # security_ip_group_attribute - (optional) is a type of string
  security_ip_group_attribute = var.security_ip_group_attribute
  # security_ip_group_name - (optional) is a type of string
  security_ip_group_name = var.security_ip_group_name
  # security_ips - (optional) is a type of set of string
  security_ips = var.security_ips
  # srcdb_instance_id - (optional) is a type of string
  srcdb_instance_id = var.srcdb_instance_id
  # ssl_enable - (optional) is a type of string
  ssl_enable = var.ssl_enable
  # tags - (optional) is a type of map of string
  tags = var.tags
  # vpc_auth_mode - (optional) is a type of string
  vpc_auth_mode = var.vpc_auth_mode
  # vswitch_id - (optional) is a type of string
  vswitch_id = var.vswitch_id
  # zone_id - (optional) is a type of string
  zone_id = var.zone_id

  dynamic "parameters" {
    for_each = var.parameters
    content {
      # name - (required) is a type of string
      name = parameters.value["name"]
      # value - (required) is a type of string
      value = parameters.value["value"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # update - (optional) is a type of string
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
  value       = alicloud_kvstore_instance.this.availability_zone
}

output "backup_period" {
  description = "returns a set of string"
  value       = alicloud_kvstore_instance.this.backup_period
}

output "backup_time" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.backup_time
}

output "bandwidth" {
  description = "returns a number"
  value       = alicloud_kvstore_instance.this.bandwidth
}

output "capacity" {
  description = "returns a number"
  value       = alicloud_kvstore_instance.this.capacity
}

output "connection_domain" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.connection_domain
}

output "connection_string" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.connection_string
}

output "db_instance_name" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.db_instance_name
}

output "enable_public" {
  description = "returns a bool"
  value       = alicloud_kvstore_instance.this.enable_public
}

output "end_time" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.end_time
}

output "id" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.id
}

output "instance_charge_type" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.instance_charge_type
}

output "instance_name" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.instance_name
}

output "instance_release_protection" {
  description = "returns a bool"
  value       = alicloud_kvstore_instance.this.instance_release_protection
}

output "maintain_end_time" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.maintain_end_time
}

output "maintain_start_time" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.maintain_start_time
}

output "payment_type" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.payment_type
}

output "private_ip" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.private_ip
}

output "qps" {
  description = "returns a number"
  value       = alicloud_kvstore_instance.this.qps
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.resource_group_id
}

output "security_ip_group_name" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.security_ip_group_name
}

output "status" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.status
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_kvstore_instance.this.zone_id
}

output "this" {
  value = alicloud_kvstore_instance.this
}
```

[top](#index)