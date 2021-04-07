# alicloud_db_readonly_instance

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
module "alicloud_db_readonly_instance" {
  source = "./modules/alicloud/r/alicloud_db_readonly_instance"

  # engine_version - (required) is a type of string
  engine_version = null
  # instance_name - (optional) is a type of string
  instance_name = null
  # instance_storage - (required) is a type of number
  instance_storage = null
  # instance_type - (required) is a type of string
  instance_type = null
  # master_db_instance_id - (required) is a type of string
  master_db_instance_id = null
  # resource_group_id - (optional) is a type of string
  resource_group_id = null
  # tags - (optional) is a type of map of string
  tags = {}
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
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "engine_version" {
  description = "(required)"
  type        = string
}

variable "instance_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_storage" {
  description = "(required)"
  type        = number
}

variable "instance_type" {
  description = "(required)"
  type        = string
}

variable "master_db_instance_id" {
  description = "(required)"
  type        = string
}

variable "resource_group_id" {
  description = "(optional)"
  type        = string
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
resource "alicloud_db_readonly_instance" "this" {
  # engine_version - (required) is a type of string
  engine_version = var.engine_version
  # instance_name - (optional) is a type of string
  instance_name = var.instance_name
  # instance_storage - (required) is a type of number
  instance_storage = var.instance_storage
  # instance_type - (required) is a type of string
  instance_type = var.instance_type
  # master_db_instance_id - (required) is a type of string
  master_db_instance_id = var.master_db_instance_id
  # resource_group_id - (optional) is a type of string
  resource_group_id = var.resource_group_id
  # tags - (optional) is a type of map of string
  tags = var.tags
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
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "connection_string" {
  description = "returns a string"
  value       = alicloud_db_readonly_instance.this.connection_string
}

output "engine" {
  description = "returns a string"
  value       = alicloud_db_readonly_instance.this.engine
}

output "id" {
  description = "returns a string"
  value       = alicloud_db_readonly_instance.this.id
}

output "instance_name" {
  description = "returns a string"
  value       = alicloud_db_readonly_instance.this.instance_name
}

output "port" {
  description = "returns a string"
  value       = alicloud_db_readonly_instance.this.port
}

output "resource_group_id" {
  description = "returns a string"
  value       = alicloud_db_readonly_instance.this.resource_group_id
}

output "zone_id" {
  description = "returns a string"
  value       = alicloud_db_readonly_instance.this.zone_id
}

output "this" {
  value = alicloud_db_readonly_instance.this
}
```

[top](#index)