# alicloud_slb_backend_server

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
module "alicloud_slb_backend_server" {
  source = "./modules/alicloud/r/alicloud_slb_backend_server"

  # delete_protection_validation - (optional) is a type of bool
  delete_protection_validation = null
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null

  backend_servers = [{
    server_id = null
    server_ip = null
    type      = null
    weight    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "delete_protection_validation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "backend_servers" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      server_id = string
      server_ip = string
      type      = string
      weight    = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_slb_backend_server" "this" {
  # delete_protection_validation - (optional) is a type of bool
  delete_protection_validation = var.delete_protection_validation
  # load_balancer_id - (required) is a type of string
  load_balancer_id = var.load_balancer_id

  dynamic "backend_servers" {
    for_each = var.backend_servers
    content {
      # server_id - (required) is a type of string
      server_id = backend_servers.value["server_id"]
      # server_ip - (optional) is a type of string
      server_ip = backend_servers.value["server_ip"]
      # type - (optional) is a type of string
      type = backend_servers.value["type"]
      # weight - (required) is a type of number
      weight = backend_servers.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_slb_backend_server.this.id
}

output "this" {
  value = alicloud_slb_backend_server.this
}
```

[top](#index)