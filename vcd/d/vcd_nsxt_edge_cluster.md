# vcd_nsxt_edge_cluster

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
module "vcd_nsxt_edge_cluster" {
  source = "./modules/vcd/d/vcd_nsxt_edge_cluster"

  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of NSX-T Edge Cluster"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "vcd_nsxt_edge_cluster" "this" {
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc
}
```

[top](#index)

### Outputs

```terraform
output "deployment_type" {
  description = "returns a string"
  value       = data.vcd_nsxt_edge_cluster.this.deployment_type
}

output "description" {
  description = "returns a string"
  value       = data.vcd_nsxt_edge_cluster.this.description
}

output "id" {
  description = "returns a string"
  value       = data.vcd_nsxt_edge_cluster.this.id
}

output "node_count" {
  description = "returns a number"
  value       = data.vcd_nsxt_edge_cluster.this.node_count
}

output "node_type" {
  description = "returns a string"
  value       = data.vcd_nsxt_edge_cluster.this.node_type
}

output "this" {
  value = vcd_nsxt_edge_cluster.this
}
```

[top](#index)