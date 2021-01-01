# vsphere_resource_pool

[back](../vsphere.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```hcl
terraform {
  required_providers {
    vsphere = ">= 1.24.3"
  }
}
```

[top](#index)

### Example Usage

```hcl
module "vsphere_resource_pool" {
  source = "./modules/vsphere/r/vsphere_resource_pool"

  # cpu_expandable - (optional) is a type of bool
  cpu_expandable = null
  # cpu_limit - (optional) is a type of number
  cpu_limit = null
  # cpu_reservation - (optional) is a type of number
  cpu_reservation = null
  # cpu_share_level - (optional) is a type of string
  cpu_share_level = null
  # cpu_shares - (optional) is a type of number
  cpu_shares = null
  # custom_attributes - (optional) is a type of map of string
  custom_attributes = {}
  # memory_expandable - (optional) is a type of bool
  memory_expandable = null
  # memory_limit - (optional) is a type of number
  memory_limit = null
  # memory_reservation - (optional) is a type of number
  memory_reservation = null
  # memory_share_level - (optional) is a type of string
  memory_share_level = null
  # memory_shares - (optional) is a type of number
  memory_shares = null
  # name - (required) is a type of string
  name = null
  # parent_resource_pool_id - (required) is a type of string
  parent_resource_pool_id = null
  # tags - (optional) is a type of set of string
  tags = []
}
```

[top](#index)

### Variables

```hcl
variable "cpu_expandable" {
  description = "(optional) - Determines if the reservation on a resource pool can grow beyond the specified value, if the parent resource pool has unreserved resources."
  type        = bool
  default     = null
}

variable "cpu_limit" {
  description = "(optional) - The utilization of a resource pool will not exceed this limit, even if there are available resources. Set to -1 for unlimited."
  type        = number
  default     = null
}

variable "cpu_reservation" {
  description = "(optional) - Amount of CPU (MHz) that is guaranteed available to the resource pool."
  type        = number
  default     = null
}

variable "cpu_share_level" {
  description = "(optional) - The allocation level. The level is a simplified view of shares. Levels map to a pre-determined set of numeric values for shares. Can be one of low, normal, high, or custom."
  type        = string
  default     = null
}

variable "cpu_shares" {
  description = "(optional) - The number of shares allocated. Used to determine resource allocation in case of resource contention. If this is set, cpu_share_level must be custom."
  type        = number
  default     = null
}

variable "custom_attributes" {
  description = "(optional) - A list of custom attributes to set on this resource."
  type        = map(string)
  default     = null
}

variable "memory_expandable" {
  description = "(optional) - Determines if the reservation on a resource pool can grow beyond the specified value, if the parent resource pool has unreserved resources."
  type        = bool
  default     = null
}

variable "memory_limit" {
  description = "(optional) - The utilization of a resource pool will not exceed this limit, even if there are available resources. Set to -1 for unlimited."
  type        = number
  default     = null
}

variable "memory_reservation" {
  description = "(optional) - Amount of memory (MB) that is guaranteed available to the resource pool."
  type        = number
  default     = null
}

variable "memory_share_level" {
  description = "(optional) - The allocation level. The level is a simplified view of shares. Levels map to a pre-determined set of numeric values for shares. Can be one of low, normal, high, or custom."
  type        = string
  default     = null
}

variable "memory_shares" {
  description = "(optional) - The number of shares allocated. Used to determine resource allocation in case of resource contention. If this is set, memory_share_level must be custom."
  type        = number
  default     = null
}

variable "name" {
  description = "(required) - Name of resource pool."
  type        = string
}

variable "parent_resource_pool_id" {
  description = "(required) - The ID of the root resource pool of the compute resource the resource pool is in."
  type        = string
}

variable "tags" {
  description = "(optional) - A list of tag IDs to apply to this object."
  type        = set(string)
  default     = null
}
```

[top](#index)

### Resource

```hcl
resource "vsphere_resource_pool" "this" {
  cpu_expandable          = var.cpu_expandable
  cpu_limit               = var.cpu_limit
  cpu_reservation         = var.cpu_reservation
  cpu_share_level         = var.cpu_share_level
  cpu_shares              = var.cpu_shares
  custom_attributes       = var.custom_attributes
  memory_expandable       = var.memory_expandable
  memory_limit            = var.memory_limit
  memory_reservation      = var.memory_reservation
  memory_share_level      = var.memory_share_level
  memory_shares           = var.memory_shares
  name                    = var.name
  parent_resource_pool_id = var.parent_resource_pool_id
  tags                    = var.tags
}
```

[top](#index)

### Outputs

```hcl
output "cpu_shares" {
  description = "returns a number"
  value       = vsphere_resource_pool.this.cpu_shares
}

output "id" {
  description = "returns a string"
  value       = vsphere_resource_pool.this.id
}

output "memory_shares" {
  description = "returns a number"
  value       = vsphere_resource_pool.this.memory_shares
}

output "this" {
  value = vsphere_resource_pool.this
}
```

[top](#index)