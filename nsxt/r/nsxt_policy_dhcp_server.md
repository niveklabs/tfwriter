# nsxt_policy_dhcp_server

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
    nsxt = ">= 3.1.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "nsxt_policy_dhcp_server" {
  source = "./modules/nsxt/r/nsxt_policy_dhcp_server"

  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # edge_cluster_path - (optional) is a type of string
  edge_cluster_path = null
  # lease_time - (optional) is a type of number
  lease_time = null
  # nsx_id - (optional) is a type of string
  nsx_id = null
  # preferred_edge_paths - (optional) is a type of list of string
  preferred_edge_paths = []
  # server_addresses - (optional) is a type of list of string
  server_addresses = []

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
  description = "(optional) - Description for this resource"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required) - Display name for this resource"
  type        = string
}

variable "edge_cluster_path" {
  description = "(optional) - Edge Cluster path"
  type        = string
  default     = null
}

variable "lease_time" {
  description = "(optional) - IP Address lease time in seconds"
  type        = number
  default     = null
}

variable "nsx_id" {
  description = "(optional) - NSX ID for this resource"
  type        = string
  default     = null
}

variable "preferred_edge_paths" {
  description = "(optional) - The first edge node is assigned as active edge, and second one as standby edge"
  type        = list(string)
  default     = null
}

variable "server_addresses" {
  description = "(optional) - DHCP server address in CIDR format"
  type        = list(string)
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
resource "nsxt_policy_dhcp_server" "this" {
  description          = var.description
  display_name         = var.display_name
  edge_cluster_path    = var.edge_cluster_path
  lease_time           = var.lease_time
  nsx_id               = var.nsx_id
  preferred_edge_paths = var.preferred_edge_paths
  server_addresses     = var.server_addresses

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
output "id" {
  description = "returns a string"
  value       = nsxt_policy_dhcp_server.this.id
}

output "nsx_id" {
  description = "returns a string"
  value       = nsxt_policy_dhcp_server.this.nsx_id
}

output "path" {
  description = "returns a string"
  value       = nsxt_policy_dhcp_server.this.path
}

output "revision" {
  description = "returns a number"
  value       = nsxt_policy_dhcp_server.this.revision
}

output "server_addresses" {
  description = "returns a list of string"
  value       = nsxt_policy_dhcp_server.this.server_addresses
}

output "this" {
  value = nsxt_policy_dhcp_server.this
}
```

[top](#index)