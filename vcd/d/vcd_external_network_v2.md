# vcd_external_network_v2

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_external_network_v2" {
  source = "./modules/vcd/d/vcd_external_network_v2"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vcd_external_network_v2" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.vcd_external_network_v2.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vcd_external_network_v2.this.id
}

output "ip_scope" {
  description = "returns a set of object"
  value       = data.vcd_external_network_v2.this.ip_scope
}

output "nsxt_network" {
  description = "returns a set of object"
  value       = data.vcd_external_network_v2.this.nsxt_network
}

output "vsphere_network" {
  description = "returns a set of object"
  value       = data.vcd_external_network_v2.this.vsphere_network
}

output "this" {
  value = vcd_external_network_v2.this
}
```

[top](#index)