# nsxt_policy_edge_cluster

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
module "nsxt_policy_edge_cluster" {
  source = "./modules/nsxt/d/nsxt_policy_edge_cluster"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # site_path - (optional) is a type of string
  site_path = null
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

variable "site_path" {
  description = "(optional) - Path of the site this Edge cluster belongs to"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "nsxt_policy_edge_cluster" "this" {
  # description - (optional) is a type of string
  description = var.description
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # site_path - (optional) is a type of string
  site_path = var.site_path
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.nsxt_policy_edge_cluster.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.nsxt_policy_edge_cluster.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.nsxt_policy_edge_cluster.this.id
}

output "path" {
  description = "returns a string"
  value       = data.nsxt_policy_edge_cluster.this.path
}

output "this" {
  value = nsxt_policy_edge_cluster.this
}
```

[top](#index)