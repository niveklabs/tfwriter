# vcd_nsxt_edgegateway

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
module "vcd_nsxt_edgegateway" {
  source = "./modules/vcd/d/vcd_nsxt_edgegateway"

  # edge_cluster_id - (optional) is a type of string
  edge_cluster_id = null
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
variable "edge_cluster_id" {
  description = "(optional) - NSX-T Edge Cluster ID."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Edge Gateway name"
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
data "vcd_nsxt_edgegateway" "this" {
  # edge_cluster_id - (optional) is a type of string
  edge_cluster_id = var.edge_cluster_id
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
output "dedicate_external_network" {
  description = "returns a bool"
  value       = data.vcd_nsxt_edgegateway.this.dedicate_external_network
}

output "description" {
  description = "returns a string"
  value       = data.vcd_nsxt_edgegateway.this.description
}

output "external_network_id" {
  description = "returns a string"
  value       = data.vcd_nsxt_edgegateway.this.external_network_id
}

output "id" {
  description = "returns a string"
  value       = data.vcd_nsxt_edgegateway.this.id
}

output "primary_ip" {
  description = "returns a string"
  value       = data.vcd_nsxt_edgegateway.this.primary_ip
}

output "subnet" {
  description = "returns a set of object"
  value       = data.vcd_nsxt_edgegateway.this.subnet
}

output "this" {
  value = vcd_nsxt_edgegateway.this
}
```

[top](#index)