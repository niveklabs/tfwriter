# nsxt_logical_tier1_router

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
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_logical_tier1_router" {
  source = "./modules/nsxt/d/nsxt_logical_tier1_router"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # edge_cluster_id - (optional) is a type of string
  edge_cluster_id = null
}
```

[top](#index)

### Variables

```terraform
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

variable "edge_cluster_id" {
  description = "(optional) - The ID of the edge cluster connected to this router"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_logical_tier1_router" "this" {
  description     = var.description
  display_name    = var.display_name
  edge_cluster_id = var.edge_cluster_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nsxt_logical_tier1_router.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_logical_tier1_router.this.display_name
}

output "edge_cluster_id" {
  description = "returns a string"
  value       = data.nsxt_logical_tier1_router.this.edge_cluster_id
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_logical_tier1_router.this.id
}

output "this" {
  value = nsxt_logical_tier1_router.this
}
```

[top](#index)