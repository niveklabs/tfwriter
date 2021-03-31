# nsxt_policy_tier1_gateway

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
module "nsxt_policy_tier1_gateway" {
  source = "./modules/nsxt/d/nsxt_policy_tier1_gateway"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # edge_cluster_path - (optional) is a type of string
  edge_cluster_path = null
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
  description = "(optional) - The path of the edge cluster connected to this Tier1 gateway"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_policy_tier1_gateway" "this" {
  description       = var.description
  display_name      = var.display_name
  edge_cluster_path = var.edge_cluster_path
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nsxt_policy_tier1_gateway.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_policy_tier1_gateway.this.display_name
}

output "edge_cluster_path" {
  description = "returns a string"
  value       = data.nsxt_policy_tier1_gateway.this.edge_cluster_path
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_policy_tier1_gateway.this.id
}

output "path" {
  description = "returns a string"
  value       = data.nsxt_policy_tier1_gateway.this.path
}

output "this" {
  value = nsxt_policy_tier1_gateway.this
}
```

[top](#index)