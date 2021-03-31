# nsxt_ip_pool_allocation_ip_address

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
module "nsxt_ip_pool_allocation_ip_address" {
  source = "./modules/nsxt/r/nsxt_ip_pool_allocation_ip_address"

  # allocation_id - (optional) is a type of string
  allocation_id = null
  # ip_pool_id - (required) is a type of string
  ip_pool_id = null
}
```

[top](#index)

### Variables

```terraform
variable "allocation_id" {
  description = "(optional) - IP Address that is allocated from the pool"
  type        = string
  default     = null
}

variable "ip_pool_id" {
  description = "(required) - ID of IP pool that allocation belongs to"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "nsxt_ip_pool_allocation_ip_address" "this" {
  allocation_id = var.allocation_id
  ip_pool_id    = var.ip_pool_id
}
```

[top](#index)

### Outputs

```terraform
output "allocation_id" {
  description = "returns a string"
  value       = nsxt_ip_pool_allocation_ip_address.this.allocation_id
}

output "id" {
  description = "returns a string"
  value       = nsxt_ip_pool_allocation_ip_address.this.id
}

output "this" {
  value = nsxt_ip_pool_allocation_ip_address.this
}
```

[top](#index)