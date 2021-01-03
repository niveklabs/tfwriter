# opc_compute_vnic

[back](../opc.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    opc = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "opc_compute_vnic" {
  source = "./modules/opc/d/opc_compute_vnic"

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
data "opc_compute_vnic" "this" {
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.opc_compute_vnic.this.description
}

output "id" {
  description = "returns a string"
  value       = data.opc_compute_vnic.this.id
}

output "mac_address" {
  description = "returns a string"
  value       = data.opc_compute_vnic.this.mac_address
}

output "tags" {
  description = "returns a list of string"
  value       = data.opc_compute_vnic.this.tags
}

output "transit_flag" {
  description = "returns a bool"
  value       = data.opc_compute_vnic.this.transit_flag
}

output "uri" {
  description = "returns a string"
  value       = data.opc_compute_vnic.this.uri
}

output "this" {
  value = opc_compute_vnic.this
}
```

[top](#index)