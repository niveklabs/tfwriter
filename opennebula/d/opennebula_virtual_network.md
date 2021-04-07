# opennebula_virtual_network

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opennebula = ">= 0.2.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opennebula_virtual_network" {
  source = "./modules/opennebula/d/opennebula_virtual_network"

  # description - (optional) is a type of string
  description = null
  # mtu - (optional) is a type of number
  mtu = null
  # name - (required) is a type of string
  name = null
  # tags - (optional) is a type of map of string
  tags = {}
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description of the vnet, in OpenNebula's XML or String format"
  type        = string
  default     = null
}

variable "mtu" {
  description = "(optional) - MTU of the vnet (defaut: 1500)"
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of the Virtual Network"
  type        = string
}

variable "tags" {
  description = "(optional) - Add custom tags to the resource"
  type        = map(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "opennebula_virtual_network" "this" {
  # description - (optional) is a type of string
  description = var.description
  # mtu - (optional) is a type of number
  mtu = var.mtu
  # name - (required) is a type of string
  name = var.name
  # tags - (optional) is a type of map of string
  tags = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.opennebula_virtual_network.this.id
}

output "this" {
  value = opennebula_virtual_network.this
}
```

[top](#index)