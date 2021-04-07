# sdm_node

[back](../sdm.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/sdm/r/sdm_node"


  gateway = [{
    bind_address   = null
    listen_address = null
    name           = null
    tags           = {}
    token          = null
  }]

  relay = [{
    name  = null
    tags  = {}
    token = null
  }]

  timeouts = [{
    default = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "gateway" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      bind_address   = string
      listen_address = string
      name           = string
      tags           = map(string)
      token          = string
    }
  ))
  default = []
}

variable "relay" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      name  = string
      tags  = map(string)
      token = string
    }
  ))
  default = []
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

### Resource

```terraform
resource "sdm_node" "this" {

  dynamic "gateway" {
    for_each = var.gateway
    content {
      # bind_address - (optional) is a type of string
      bind_address = gateway.value["bind_address"]
      # listen_address - (required) is a type of string
      listen_address = gateway.value["listen_address"]
      # name - (optional) is a type of string
      name = gateway.value["name"]
      # tags - (optional) is a type of map of string
      tags = gateway.value["tags"]
    }
  }

  dynamic "relay" {
    for_each = var.relay
    content {
      # name - (optional) is a type of string
      name = relay.value["name"]
      # tags - (optional) is a type of map of string
      tags = relay.value["tags"]
    }
  }

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
  value       = sdm_node.this.id
}

output "this" {
  value = sdm_node.this
}
```

[top](#index)