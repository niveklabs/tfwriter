# bigip_ltm_node

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/bigip/d/bigip_ltm_node"

  # address - (optional) is a type of string
  address = null
  # description - (optional) is a type of string
  description = null
  # name - (required) is a type of string
  name = null
  # partition - (required) is a type of string
  partition = null

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
  description = "(optional) - IP address of the node of the node."
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - User defined description of the node."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Name of the node."
  type        = string
}

variable "partition" {
  description = "(required) - Partition of resource group"
  type        = string
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

### Datasource

```terraform
data "bigip_ltm_node" "this" {
  address     = var.address
  description = var.description
  name        = var.name
  partition   = var.partition

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
  value       = data.bigip_ltm_node.this.connection_limit
}

output "dynamic_ratio" {
  description = "returns a number"
  value       = data.bigip_ltm_node.this.dynamic_ratio
}

output "id" {
  description = "returns a string"
  value       = data.bigip_ltm_node.this.id
}

output "monitor" {
  description = "returns a string"
  value       = data.bigip_ltm_node.this.monitor
}

output "rate_limit" {
  description = "returns a string"
  value       = data.bigip_ltm_node.this.rate_limit
}

output "ratio" {
  description = "returns a number"
  value       = data.bigip_ltm_node.this.ratio
}

output "state" {
  description = "returns a string"
  value       = data.bigip_ltm_node.this.state
}

output "this" {
  value = bigip_ltm_node.this
}
```

[top](#index)