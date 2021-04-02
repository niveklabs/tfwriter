# bigip_ltm_node

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
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_node" {
  source = "./modules/bigip/r/bigip_ltm_node"

  # address - (required) is a type of string
  address = null
  # connection_limit - (optional) is a type of number
  connection_limit = null
  # description - (optional) is a type of string
  description = null
  # dynamic_ratio - (optional) is a type of number
  dynamic_ratio = null
  # monitor - (optional) is a type of string
  monitor = null
  # name - (required) is a type of string
  name = null
  # rate_limit - (optional) is a type of string
  rate_limit = null
  # ratio - (optional) is a type of number
  ratio = null
  # state - (optional) is a type of string
  state = null

  fqdn = [{
    address_family = null
    autopopulate   = null
    downinterval   = null
    interval       = null
    name           = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required) - Address of the node"
  type        = string
}

variable "connection_limit" {
  description = "(optional) - Specifies the maximum number of connections allowed for the node or node address."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - User defined description of the node."
  type        = string
  default     = null
}

variable "dynamic_ratio" {
  description = "(optional) - Sets the dynamic ratio number for the node. Used for dynamic ratio load balancing. "
  type        = number
  default     = null
}

variable "monitor" {
  description = "(optional) - Specifies the name of the monitor or monitor rule that you want to associate with the node."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the node"
  type        = string
}

variable "rate_limit" {
  description = "(optional) - Specifies the maximum number of connections per second allowed for a node or node address. The default value is 'disabled'."
  type        = string
  default     = null
}

variable "ratio" {
  description = "(optional) - Sets the ratio number for the node."
  type        = number
  default     = null
}

variable "state" {
  description = "(optional) - Marks the node up or down. The default value is user-up."
  type        = string
  default     = null
}

variable "fqdn" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      address_family = string
      autopopulate   = string
      downinterval   = number
      interval       = string
      name           = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_node" "this" {
  address          = var.address
  connection_limit = var.connection_limit
  description      = var.description
  dynamic_ratio    = var.dynamic_ratio
  monitor          = var.monitor
  name             = var.name
  rate_limit       = var.rate_limit
  ratio            = var.ratio
  state            = var.state

  dynamic "fqdn" {
    for_each = var.fqdn
    content {
      address_family = fqdn.value["address_family"]
      autopopulate   = fqdn.value["autopopulate"]
      downinterval   = fqdn.value["downinterval"]
      interval       = fqdn.value["interval"]
      name           = fqdn.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "connection_limit" {
  description = "returns a number"
  value       = bigip_ltm_node.this.connection_limit
}

output "dynamic_ratio" {
  description = "returns a number"
  value       = bigip_ltm_node.this.dynamic_ratio
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_node.this.id
}

output "rate_limit" {
  description = "returns a string"
  value       = bigip_ltm_node.this.rate_limit
}

output "ratio" {
  description = "returns a number"
  value       = bigip_ltm_node.this.ratio
}

output "this" {
  value = bigip_ltm_node.this
}
```

[top](#index)