# alicloud_gpdb_connection

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
module "alicloud_gpdb_connection" {
  source = "./modules/alicloud/r/alicloud_gpdb_connection"

  # connection_prefix - (optional) is a type of string
  connection_prefix = null
  # instance_id - (required) is a type of string
  instance_id = null
  # port - (optional) is a type of string
  port = null

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
variable "connection_prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "port" {
  description = "(optional)"
  type        = string
  default     = null
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
resource "alicloud_gpdb_connection" "this" {
  connection_prefix = var.connection_prefix
  instance_id       = var.instance_id
  port              = var.port

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
output "connection_prefix" {
  description = "returns a string"
  value       = alicloud_gpdb_connection.this.connection_prefix
}

output "connection_string" {
  description = "returns a string"
  value       = alicloud_gpdb_connection.this.connection_string
}

output "id" {
  description = "returns a string"
  value       = alicloud_gpdb_connection.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = alicloud_gpdb_connection.this.ip_address
}

output "this" {
  value = alicloud_gpdb_connection.this
}
```

[top](#index)