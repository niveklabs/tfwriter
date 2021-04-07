# sdm_node

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    sdm = ">= 1.0.19"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "sdm_node" {
  source = "./modules/sdm/d/sdm_node"

  # bind_address - (optional) is a type of string
  bind_address = null
  # listen_address - (optional) is a type of string
  listen_address = null
  # name - (optional) is a type of string
  name = null
  # type - (optional) is a type of string
  type = null

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "bind_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "listen_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      default = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "sdm_node" "this" {
  # bind_address - (optional) is a type of string
  bind_address = var.bind_address
  # listen_address - (optional) is a type of string
  listen_address = var.listen_address
  # name - (optional) is a type of string
  name = var.name
  # type - (optional) is a type of string
  type = var.type

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # default - (optional) is a type of string
      default = timeouts.value["default"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.sdm_node.this.id
}

output "ids" {
  description = "returns a list of string"
  value       = data.sdm_node.this.ids
}

output "nodes" {
  description = "returns a list of object"
  value       = data.sdm_node.this.nodes
}

output "this" {
  value = sdm_node.this
}
```

[top](#index)