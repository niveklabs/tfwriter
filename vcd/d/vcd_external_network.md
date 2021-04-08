# vcd_external_network

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
module "vcd_external_network" {
  source = "./modules/vcd/d/vcd_external_network"

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
data "vcd_external_network" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.vcd_external_network.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vcd_external_network.this.id
}

output "ip_scope" {
  description = "returns a list of object"
  value       = data.vcd_external_network.this.ip_scope
}

output "retain_net_info_across_deployments" {
  description = "returns a bool"
  value       = data.vcd_external_network.this.retain_net_info_across_deployments
}

output "vsphere_network" {
  description = "returns a list of object"
  value       = data.vcd_external_network.this.vsphere_network
}

output "this" {
  value = vcd_external_network.this
}
```

[top](#index)