# aviatrix_gateway_dnat

[back](../aviatrix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    aviatrix = ">= 2.17.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_gateway_dnat" {
  source = "./modules/aviatrix/r/aviatrix_gateway_dnat"

  # gw_name - (required) is a type of string
  gw_name = null
  # sync_to_ha - (optional) is a type of bool
  sync_to_ha = null

  dnat_policy = [{
    connection  = null
    dnat_ips    = null
    dnat_port   = null
    dst_cidr    = null
    dst_port    = null
    exclude_rtb = null
    interface   = null
    mark        = null
    protocol    = null
    src_cidr    = null
    src_port    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "gw_name" {
  description = "(required) - Name of the gateway."
  type        = string
}

variable "sync_to_ha" {
  description = "(optional) - Whether to sync the policies to the HA gateway."
  type        = bool
  default     = null
}

variable "dnat_policy" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      connection  = string
      dnat_ips    = string
      dnat_port   = string
      dst_cidr    = string
      dst_port    = string
      exclude_rtb = string
      interface   = string
      mark        = string
      protocol    = string
      src_cidr    = string
      src_port    = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_gateway_dnat" "this" {
  gw_name    = var.gw_name
  sync_to_ha = var.sync_to_ha

  dynamic "dnat_policy" {
    for_each = var.dnat_policy
    content {
      connection  = dnat_policy.value["connection"]
      dnat_ips    = dnat_policy.value["dnat_ips"]
      dnat_port   = dnat_policy.value["dnat_port"]
      dst_cidr    = dnat_policy.value["dst_cidr"]
      dst_port    = dnat_policy.value["dst_port"]
      exclude_rtb = dnat_policy.value["exclude_rtb"]
      interface   = dnat_policy.value["interface"]
      mark        = dnat_policy.value["mark"]
      protocol    = dnat_policy.value["protocol"]
      src_cidr    = dnat_policy.value["src_cidr"]
      src_port    = dnat_policy.value["src_port"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_gateway_dnat.this.id
}

output "this" {
  value = aviatrix_gateway_dnat.this
}
```

[top](#index)