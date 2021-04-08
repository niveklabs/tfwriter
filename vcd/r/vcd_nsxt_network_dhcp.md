# vcd_nsxt_network_dhcp

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "vcd_nsxt_network_dhcp" {
  source = "./modules/vcd/r/vcd_nsxt_network_dhcp"

  # org - (optional) is a type of string
  org = null
  # org_network_id - (required) is a type of string
  org_network_id = null
  # vdc - (optional) is a type of string
  vdc = null

  pool = [{
    end_address   = null
    start_address = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "org_network_id" {
  description = "(required) - Parent Org VDC network ID"
  type        = string
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "pool" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      end_address   = string
      start_address = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "vcd_nsxt_network_dhcp" "this" {
  # org - (optional) is a type of string
  org = var.org
  # org_network_id - (required) is a type of string
  org_network_id = var.org_network_id
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "pool" {
    for_each = var.pool
    content {
      # end_address - (required) is a type of string
      end_address = pool.value["end_address"]
      # start_address - (required) is a type of string
      start_address = pool.value["start_address"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_nsxt_network_dhcp.this.id
}

output "this" {
  value = vcd_nsxt_network_dhcp.this
}
```

[top](#index)