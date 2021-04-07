# opennebula_virtual_data_center

[back](../opennebula.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "opennebula_virtual_data_center" {
  source = "./modules/opennebula/r/opennebula_virtual_data_center"

  # group_ids - (optional) is a type of list of number
  group_ids = []
  # name - (required) is a type of string
  name = null

  zones = [{
    cluster_ids   = []
    datastore_ids = []
    host_ids      = []
    id            = null
    vnet_ids      = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "group_ids" {
  description = "(optional) - List of Group IDs to be added into the VDC"
  type        = list(number)
  default     = null
}

variable "name" {
  description = "(required) - Name of the VDC"
  type        = string
}

variable "zones" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      cluster_ids   = list(number)
      datastore_ids = list(number)
      host_ids      = list(number)
      id            = number
      vnet_ids      = list(number)
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "opennebula_virtual_data_center" "this" {
  # group_ids - (optional) is a type of list of number
  group_ids = var.group_ids
  # name - (required) is a type of string
  name = var.name

  dynamic "zones" {
    for_each = var.zones
    content {
      # cluster_ids - (optional) is a type of list of number
      cluster_ids = zones.value["cluster_ids"]
      # datastore_ids - (optional) is a type of list of number
      datastore_ids = zones.value["datastore_ids"]
      # host_ids - (optional) is a type of list of number
      host_ids = zones.value["host_ids"]
      # id - (optional) is a type of number
      id = zones.value["id"]
      # vnet_ids - (optional) is a type of list of number
      vnet_ids = zones.value["vnet_ids"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "group_ids" {
  description = "returns a list of number"
  value       = opennebula_virtual_data_center.this.group_ids
}

output "id" {
  description = "returns a string"
  value       = opennebula_virtual_data_center.this.id
}

output "this" {
  value = opennebula_virtual_data_center.this
}
```

[top](#index)