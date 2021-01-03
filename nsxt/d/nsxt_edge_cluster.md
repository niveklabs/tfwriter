# nsxt_edge_cluster

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    nsxt = ">= 3.1.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_edge_cluster" {
  source = "./modules/nsxt/d/nsxt_edge_cluster"

  # deployment_type - (optional) is a type of string
  deployment_type = null
  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # member_node_type - (optional) is a type of string
  member_node_type = null
}
```

[top](#index)

### Variables

```terraform
variable "deployment_type" {
  description = "(optional) - The deployment type of edge cluster members (UNKNOWN/VIRTUAL_MACHINE|PHYSICAL_MACHINE)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional) - Description of this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - The display name of this resource"
  type        = string
  default     = null
}

variable "member_node_type" {
  description = "(optional) - Type of transport nodes"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_edge_cluster" "this" {
  deployment_type  = var.deployment_type
  description      = var.description
  display_name     = var.display_name
  member_node_type = var.member_node_type
}
```

[top](#index)

### Outputs

```terraform
output "deployment_type" {
  description = "returns a string"
  value       = data.nsxt_edge_cluster.this.deployment_type
}

output "description" {
  description = "returns a string"
  value       = data.nsxt_edge_cluster.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_edge_cluster.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_edge_cluster.this.id
}

output "member_node_type" {
  description = "returns a string"
  value       = data.nsxt_edge_cluster.this.member_node_type
}

output "this" {
  value = nsxt_edge_cluster.this
}
```

[top](#index)