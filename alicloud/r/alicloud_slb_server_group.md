# alicloud_slb_server_group

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
module "alicloud_slb_server_group" {
  source = "./modules/alicloud/r/alicloud_slb_server_group"

  # delete_protection_validation - (optional) is a type of bool
  delete_protection_validation = null
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # name - (optional) is a type of string
  name = null

  servers = [{
    port       = null
    server_ids = []
    type       = null
    weight     = null
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

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "servers" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      port       = number
      server_ids = list(string)
      type       = string
      weight     = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "alicloud_slb_server_group" "this" {
  delete_protection_validation = var.delete_protection_validation
  load_balancer_id             = var.load_balancer_id
  name                         = var.name

  dynamic "servers" {
    for_each = var.servers
    content {
      port       = servers.value["port"]
      server_ids = servers.value["server_ids"]
      type       = servers.value["type"]
      weight     = servers.value["weight"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = alicloud_slb_server_group.this.id
}

output "this" {
  value = alicloud_slb_server_group.this
}
```

[top](#index)