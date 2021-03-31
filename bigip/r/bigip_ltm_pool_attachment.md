# bigip_ltm_pool_attachment

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_pool_attachment" {
  source = "./modules/bigip/r/bigip_ltm_pool_attachment"

  # connection_limit - (optional) is a type of number
  connection_limit = null
  # connection_rate_limit - (optional) is a type of string
  connection_rate_limit = null
  # dynamic_ratio - (optional) is a type of number
  dynamic_ratio = null
  # fqdn_autopopulate - (optional) is a type of string
  fqdn_autopopulate = null
  # node - (required) is a type of string
  node = null
  # pool - (required) is a type of string
  pool = null
  # priority_group - (optional) is a type of number
  priority_group = null
  # ratio - (optional) is a type of number
  ratio = null
}
```

[top](#index)

### Variables

```terraform
variable "connection_limit" {
  description = "(optional) - Specifies a maximum established connection limit for a pool member or node. When the current connections count reaches this number, the system does not send additional connections to that pool member or node. The default is 0, meaning that there is no limit to the number of connections. When used with the weighted least connections load balancing methods, the system uses connection limits to determine the proportional load of each pool member or node. This must be a value other than 0 when specified for the weighted least connections load balancing methods"
  type        = number
  default     = null
}

variable "connection_rate_limit" {
  description = "(optional) - Specifies the maximum number of connections-per-second allowed for a pool member. When the number of connections-per-second reaches the limit for a given pool member, the system drops (UDP) or resets (TCP) additional connection requests. This helps detect Denial of Service attacks, where connection requests flood a pool member. Setting this to 0 turns off connection limits. The default is 0."
  type        = string
  default     = null
}

variable "dynamic_ratio" {
  description = "(optional) - Sets the dynamic ratio number for the node. Used for dynamic ratio load balancing. "
  type        = number
  default     = null
}

variable "fqdn_autopopulate" {
  description = "(optional) - Specifies whether the node should scale to the IP address set returned by DNS."
  type        = string
  default     = null
}

variable "node" {
  description = "(required) - Poolmember to add/remove to/from the pool. Format node_address:port. e.g 1.1.1.1:80"
  type        = string
}

variable "pool" {
  description = "(required) - Name of the pool to be attached with pool members"
  type        = string
}

variable "priority_group" {
  description = "(optional) - Specifies a number representing the priority group for the pool member. The default is 0, meaning that the member has no priority. To specify a priority, you must activate priority group usage when you create a new pool or when adding or removing pool members. When activated, the system load balances traffic according to the priority group number assigned to the pool member. The higher the number, the higher the priority, so a member with a priority of 3 has higher priority than a member with a priority of 1."
  type        = number
  default     = null
}

variable "ratio" {
  description = "(optional) - Specifies the ratio weight to assign to the pool member. Valid values range from 1 through 65535. The default is 1, which means that each pool member has an equal ratio proportion."
  type        = number
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_pool_attachment" "this" {
  connection_limit      = var.connection_limit
  connection_rate_limit = var.connection_rate_limit
  dynamic_ratio         = var.dynamic_ratio
  fqdn_autopopulate     = var.fqdn_autopopulate
  node                  = var.node
  pool                  = var.pool
  priority_group        = var.priority_group
  ratio                 = var.ratio
}
```

[top](#index)

### Outputs

```terraform
output "connection_limit" {
  description = "returns a number"
  value       = bigip_ltm_pool_attachment.this.connection_limit
}

output "connection_rate_limit" {
  description = "returns a string"
  value       = bigip_ltm_pool_attachment.this.connection_rate_limit
}

output "dynamic_ratio" {
  description = "returns a number"
  value       = bigip_ltm_pool_attachment.this.dynamic_ratio
}

output "id" {
  description = "returns a string"
  value       = bigip_ltm_pool_attachment.this.id
}

output "priority_group" {
  description = "returns a number"
  value       = bigip_ltm_pool_attachment.this.priority_group
}

output "ratio" {
  description = "returns a number"
  value       = bigip_ltm_pool_attachment.this.ratio
}

output "this" {
  value = bigip_ltm_pool_attachment.this
}
```

[top](#index)