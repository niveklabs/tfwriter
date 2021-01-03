# linode_nodebalancer

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
    linode = ">= 1.13.4"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "linode_nodebalancer" {
  source = "./modules/linode/r/linode_nodebalancer"

  # client_conn_throttle - (optional) is a type of number
  client_conn_throttle = null
  # label - (optional) is a type of string
  label = null
  # region - (required) is a type of string
  region = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```terraform
variable "client_conn_throttle" {
  description = "(optional) - Throttle connections per second (0-20). Set to 0 (zero) to disable throttling."
  type        = number
  default     = null
}

variable "label" {
  description = "(optional) - The label of the Linode NodeBalancer."
  type        = string
  default     = null
}

variable "region" {
  description = "(required) - The region where this NodeBalancer will be deployed."
  type        = string
}

variable "tags" {
  description = "(optional) - An array of tags applied to this object. Tags are for organizational purposes only."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "linode_nodebalancer" "this" {
  client_conn_throttle = var.client_conn_throttle
  label                = var.label
  region               = var.region
  tags                 = var.tags
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = linode_nodebalancer.this.created
}

output "hostname" {
  description = "returns a string"
  value       = linode_nodebalancer.this.hostname
}

output "id" {
  description = "returns a string"
  value       = linode_nodebalancer.this.id
}

output "ipv4" {
  description = "returns a string"
  value       = linode_nodebalancer.this.ipv4
}

output "ipv6" {
  description = "returns a string"
  value       = linode_nodebalancer.this.ipv6
}

output "transfer" {
  description = "returns a map of string"
  value       = linode_nodebalancer.this.transfer
}

output "updated" {
  description = "returns a string"
  value       = linode_nodebalancer.this.updated
}

output "this" {
  value = linode_nodebalancer.this
}
```

[top](#index)