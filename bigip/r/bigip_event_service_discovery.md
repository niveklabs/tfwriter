# bigip_event_service_discovery

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.5.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_event_service_discovery" {
  source = "./modules/bigip/r/bigip_event_service_discovery"

  # taskid - (required) is a type of string
  taskid = null

  node = [{
    id   = null
    ip   = null
    port = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "taskid" {
  description = "(required) - Name of the partition/tenant"
  type        = string
}

variable "node" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      id   = string
      ip   = string
      port = number
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "bigip_event_service_discovery" "this" {
  taskid = var.taskid

  dynamic "node" {
    for_each = var.node
    content {
      id   = node.value["id"]
      ip   = node.value["ip"]
      port = node.value["port"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_event_service_discovery.this.id
}

output "this" {
  value = bigip_event_service_discovery.this
}
```

[top](#index)