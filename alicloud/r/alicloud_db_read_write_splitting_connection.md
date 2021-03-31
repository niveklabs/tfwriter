# alicloud_db_read_write_splitting_connection

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
module "alicloud_db_read_write_splitting_connection" {
  source = "./modules/alicloud/r/alicloud_db_read_write_splitting_connection"

  # connection_prefix - (optional) is a type of string
  connection_prefix = null
  # distribution_type - (required) is a type of string
  distribution_type = null
  # instance_id - (required) is a type of string
  instance_id = null
  # max_delay_time - (optional) is a type of number
  max_delay_time = null
  # port - (optional) is a type of number
  port = null
  # weight - (optional) is a type of map of string
  weight = {}
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

variable "distribution_type" {
  description = "(required)"
  type        = string
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "max_delay_time" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "weight" {
  description = "(optional)"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_db_read_write_splitting_connection" "this" {
  connection_prefix = var.connection_prefix
  distribution_type = var.distribution_type
  instance_id       = var.instance_id
  max_delay_time    = var.max_delay_time
  port              = var.port
  weight            = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "connection_string" {
  description = "returns a string"
  value       = alicloud_db_read_write_splitting_connection.this.connection_string
}

output "id" {
  description = "returns a string"
  value       = alicloud_db_read_write_splitting_connection.this.id
}

output "max_delay_time" {
  description = "returns a number"
  value       = alicloud_db_read_write_splitting_connection.this.max_delay_time
}

output "port" {
  description = "returns a number"
  value       = alicloud_db_read_write_splitting_connection.this.port
}

output "this" {
  value = alicloud_db_read_write_splitting_connection.this
}
```

[top](#index)