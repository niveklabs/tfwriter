# vcd_nsxt_tier0_router

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_nsxt_tier0_router" {
  source = "./modules/vcd/d/vcd_nsxt_tier0_router"

  # name - (required) is a type of string
  name = null
  # nsxt_manager_id - (required) is a type of string
  nsxt_manager_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of NSX-T Tier-0 router."
  type        = string
}

variable "nsxt_manager_id" {
  description = "(required) - ID of NSX-T manager."
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "vcd_nsxt_tier0_router" "this" {
  # name - (required) is a type of string
  name = var.name
  # nsxt_manager_id - (required) is a type of string
  nsxt_manager_id = var.nsxt_manager_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.vcd_nsxt_tier0_router.this.id
}

output "is_assigned" {
  description = "returns a bool"
  value       = data.vcd_nsxt_tier0_router.this.is_assigned
}

output "this" {
  value = vcd_nsxt_tier0_router.this
}
```

[top](#index)