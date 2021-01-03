# nsxt_dhcp_server_profile

[back](../nsxt.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "nsxt_dhcp_server_profile" {
  source = "./modules/nsxt/r/nsxt_dhcp_server_profile"

  # description - (optional) is a type of string
  description = null
  # display_name - (optional) is a type of string
  display_name = null
  # edge_cluster_id - (required) is a type of string
  edge_cluster_id = null
  # edge_cluster_member_indexes - (optional) is a type of list of number
  edge_cluster_member_indexes = []

  tag = [{
    scope = null
    tag   = null
  }]
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
  description = "(optional) - The display name of this resource. Defaults to ID if not set"
  type        = string
  default     = null
}

variable "edge_cluster_id" {
  description = "(required) - Edge cluster uuid"
  type        = string
}

variable "edge_cluster_member_indexes" {
  description = "(optional) - Edge nodes from the given cluster"
  type        = list(number)
  default     = null
}

variable "tag" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      scope = string
      tag   = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_dhcp_server_profile" "this" {
  description                 = var.description
  display_name                = var.display_name
  edge_cluster_id             = var.edge_cluster_id
  edge_cluster_member_indexes = var.edge_cluster_member_indexes

  dynamic "tag" {
    for_each = var.tag
    content {
      scope = tag.value["scope"]
      tag   = tag.value["tag"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = nsxt_dhcp_server_profile.this.display_name
}

output "id" {
  description = "returns a string"
  value       = nsxt_dhcp_server_profile.this.id
}

output "revision" {
  description = "returns a number"
  value       = nsxt_dhcp_server_profile.this.revision
}

output "this" {
  value = nsxt_dhcp_server_profile.this
}
```

[top](#index)