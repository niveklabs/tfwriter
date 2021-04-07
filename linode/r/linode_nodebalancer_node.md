# linode_nodebalancer_node

[back](../linode.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    linode = ">= 1.16.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_nodebalancer_node" {
  source = "./modules/linode/r/linode_nodebalancer_node"

  # address - (required) is a type of string
  address = null
  # config_id - (required) is a type of number
  config_id = null
  # label - (required) is a type of string
  label = null
  # mode - (optional) is a type of string
  mode = null
  # nodebalancer_id - (required) is a type of number
  nodebalancer_id = null
  # weight - (optional) is a type of number
  weight = null
}
```

[top](#index)

### Variables

```terraform
variable "address" {
  description = "(required) - The private IP Address and port (IP:PORT) where this backend can be reached. This must be a private IP address."
  type        = string
}

variable "config_id" {
  description = "(required) - The ID of the NodeBalancerConfig to access."
  type        = number
}

variable "label" {
  description = "(required) - The label for this node. This is for display purposes only."
  type        = string
}

variable "mode" {
  description = "(optional) - The mode this NodeBalancer should use when sending traffic to this backend. If set to `accept` this backend is accepting traffic. If set to `reject` this backend will not receive traffic. If set to `drain` this backend will not receive new traffic, but connections already pinned to it will continue to be routed to it. If set to `backup` this backend will only accept traffic if all other nodes are down."
  type        = string
  default     = null
}

variable "nodebalancer_id" {
  description = "(required) - The ID of the NodeBalancer to access."
  type        = number
}

variable "weight" {
  description = "(optional) - Used when picking a backend to serve a request and is not pinned to a single backend yet. Nodes with a higher weight will receive more traffic. (1-255)"
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "linode_nodebalancer_node" "this" {
  # address - (required) is a type of string
  address = var.address
  # config_id - (required) is a type of number
  config_id = var.config_id
  # label - (required) is a type of string
  label = var.label
  # mode - (optional) is a type of string
  mode = var.mode
  # nodebalancer_id - (required) is a type of number
  nodebalancer_id = var.nodebalancer_id
  # weight - (optional) is a type of number
  weight = var.weight
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = linode_nodebalancer_node.this.id
}

output "mode" {
  description = "returns a string"
  value       = linode_nodebalancer_node.this.mode
}

output "status" {
  description = "returns a string"
  value       = linode_nodebalancer_node.this.status
}

output "weight" {
  description = "returns a number"
  value       = linode_nodebalancer_node.this.weight
}

output "this" {
  value = linode_nodebalancer_node.this
}
```

[top](#index)