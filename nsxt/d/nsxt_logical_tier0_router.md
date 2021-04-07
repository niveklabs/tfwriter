# nsxt_logical_tier0_router

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
module "nsxt_logical_tier0_router" {
  source = "./modules/nsxt/d/nsxt_logical_tier0_router"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # edge_cluster_id - (optional) is a type of string
  edge_cluster_id = null
  # high_availability_mode - (optional) is a type of string
  high_availability_mode = null
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

variable "high_availability_mode" {
  description = "(optional) - The High availability mode of this router"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_logical_tier0_router" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # edge_cluster_id - (optional) is a type of string
  edge_cluster_id = var.edge_cluster_id
  # high_availability_mode - (optional) is a type of string
  high_availability_mode = var.high_availability_mode
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nsxt_logical_tier0_router.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_logical_tier0_router.this.display_name
}

output "edge_cluster_id" {
  description = "returns a string"
  value       = data.nsxt_logical_tier0_router.this.edge_cluster_id
}

output "high_availability_mode" {
  description = "returns a string"
  value       = data.nsxt_logical_tier0_router.this.high_availability_mode
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_logical_tier0_router.this.id
}

output "this" {
  value = nsxt_logical_tier0_router.this
}
```

[top](#index)