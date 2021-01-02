# aws_db_proxy_default_target_group

[back](../aws.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aws = ">= 3.22.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aws_db_proxy_default_target_group" {
  source = "./modules/aws/r/aws_db_proxy_default_target_group"

  # db_proxy_name - (required) is a type of string
  db_proxy_name = null

  connection_pool_config = [{
    connection_borrow_timeout    = null
    init_query                   = null
    max_connections_percent      = null
    max_idle_connections_percent = null
    session_pinning_filters      = []
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
variable "db_proxy_name" {
  description = "(required)"
  type        = string
}

variable "connection_pool_config" {
  description = "nested mode: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      connection_borrow_timeout    = number
      init_query                   = string
      max_connections_percent      = number
      max_idle_connections_percent = number
      session_pinning_filters      = set(string)
    }
  ))
  default = []
}

variable "timeouts" {
  description = "nested mode: NestingSingle, min items: 0, max items: 0"
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
resource "aws_db_proxy_default_target_group" "this" {
  db_proxy_name = var.db_proxy_name

  dynamic "connection_pool_config" {
    for_each = var.connection_pool_config
    content {
      connection_borrow_timeout    = connection_pool_config.value["connection_borrow_timeout"]
      init_query                   = connection_pool_config.value["init_query"]
      max_connections_percent      = connection_pool_config.value["max_connections_percent"]
      max_idle_connections_percent = connection_pool_config.value["max_idle_connections_percent"]
      session_pinning_filters      = connection_pool_config.value["session_pinning_filters"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "arn" {
  description = "returns a string"
  value       = aws_db_proxy_default_target_group.this.arn
}

output "id" {
  description = "returns a string"
  value       = aws_db_proxy_default_target_group.this.id
}

output "name" {
  description = "returns a string"
  value       = aws_db_proxy_default_target_group.this.name
}

output "this" {
  value = aws_db_proxy_default_target_group.this
}
```

[top](#index)