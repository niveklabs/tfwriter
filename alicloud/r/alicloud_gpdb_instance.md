# alicloud_gpdb_instance

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
module "alicloud_gpdb_instance" {
  source = "./modules/alicloud/r/alicloud_gpdb_instance"

  # availability_zone - (optional) is a type of string
  availability_zone = null
  # description - (optional) is a type of string
  description = null
  # engine - (optional) is a type of string
  engine = null
  # engine_version - (optional) is a type of string
  engine_version = null
  # instance_charge_type - (optional) is a type of string
  instance_charge_type = null
  # instance_class - (required) is a type of string
  instance_class = null
  # instance_group_count - (required) is a type of string
  instance_group_count = null
  # security_ip_list - (optional) is a type of set of string
  security_ip_list = []
  # tags - (optional) is a type of map of string
  tags = {}
  # vswitch_id - (optional) is a type of string
  vswitch_id = null

  timeouts = [{
    create = null
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "engine_version" {
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
  description = "(required)"
  type        = string
}

variable "instance_group_count" {
  description = "(required)"
  type        = string
}

variable "security_ip_list" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "vswitch_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_gpdb_instance" "this" {
  availability_zone    = var.availability_zone
  description          = var.description
  engine               = var.engine
  engine_version       = var.engine_version
  instance_charge_type = var.instance_charge_type
  instance_class       = var.instance_class
  instance_group_count = var.instance_group_count
  security_ip_list     = var.security_ip_list
  tags                 = var.tags
  vswitch_id           = var.vswitch_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "availability_zone" {
  description = "returns a string"
  value       = alicloud_gpdb_instance.this.availability_zone
}

output "engine" {
  description = "returns a string"
  value       = alicloud_gpdb_instance.this.engine
}

output "engine_version" {
  description = "returns a string"
  value       = alicloud_gpdb_instance.this.engine_version
}

output "id" {
  description = "returns a string"
  value       = alicloud_gpdb_instance.this.id
}

output "instance_charge_type" {
  description = "returns a string"
  value       = alicloud_gpdb_instance.this.instance_charge_type
}

output "security_ip_list" {
  description = "returns a set of string"
  value       = alicloud_gpdb_instance.this.security_ip_list
}

output "vswitch_id" {
  description = "returns a string"
  value       = alicloud_gpdb_instance.this.vswitch_id
}

output "this" {
  value = alicloud_gpdb_instance.this
}
```

[top](#index)