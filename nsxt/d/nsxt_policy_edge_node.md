# nsxt_policy_edge_node

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
module "nsxt_policy_edge_node" {
  source = "./modules/nsxt/d/nsxt_policy_edge_node"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # edge_cluster_path - (required) is a type of string
  edge_cluster_path = null
  # member_index - (optional) is a type of number
  member_index = null
}
```

[top](#index)

### Variables

```terraform
variable "description" {
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional) - Display name of this resource"
  type        = string
  default     = null
}

variable "edge_cluster_path" {
  description = "(required) - Edge cluster Path"
  type        = string
}

variable "member_index" {
  description = "(optional) - Index of this node within edge cluster"
  type        = number
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_policy_edge_node" "this" {
  description       = var.description
  display_name      = var.display_name
  edge_cluster_path = var.edge_cluster_path
  member_index      = var.member_index
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nsxt_policy_edge_node.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_policy_edge_node.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_policy_edge_node.this.id
}

output "path" {
  description = "returns a string"
  value       = data.nsxt_policy_edge_node.this.path
}

output "this" {
  value = nsxt_policy_edge_node.this
}
```

[top](#index)