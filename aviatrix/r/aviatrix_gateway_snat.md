# aviatrix_gateway_snat

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
    aviatrix = ">= 2.18.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "aviatrix_gateway_snat" {
  source = "./modules/aviatrix/r/aviatrix_gateway_snat"

  # gw_name - (required) is a type of string
  gw_name = null
  # snat_mode - (optional) is a type of string
  snat_mode = null
  # sync_to_ha - (optional) is a type of bool
  sync_to_ha = null

  snat_policy = [{
    connection  = null
    dst_cidr    = null
    dst_port    = null
    exclude_rtb = null
    interface   = null
    mark        = null
    protocol    = null
    snat_ips    = null
    snat_port   = null
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

variable "snat_mode" {
  description = "(optional) - Nat mode. Currently only supports 'customized_snat'."
  type        = string
  default     = null
}

variable "sync_to_ha" {
  description = "(optional) - Whether to sync the policies to the HA gateway."
  type        = bool
  default     = null
}

variable "snat_policy" {
  description = "nested block: NestingList, min items: 0, max items: 0"
  type = set(object(
    {
      connection  = string
      dst_cidr    = string
      dst_port    = string
      exclude_rtb = string
      interface   = string
      mark        = string
      protocol    = string
      snat_ips    = string
      snat_port   = string
      src_cidr    = string
      src_port    = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "aviatrix_gateway_snat" "this" {
  # gw_name - (required) is a type of string
  gw_name = var.gw_name
  # snat_mode - (optional) is a type of string
  snat_mode = var.snat_mode
  # sync_to_ha - (optional) is a type of bool
  sync_to_ha = var.sync_to_ha

  dynamic "snat_policy" {
    for_each = var.snat_policy
    content {
      # connection - (optional) is a type of string
      connection = snat_policy.value["connection"]
      # dst_cidr - (optional) is a type of string
      dst_cidr = snat_policy.value["dst_cidr"]
      # dst_port - (optional) is a type of string
      dst_port = snat_policy.value["dst_port"]
      # exclude_rtb - (optional) is a type of string
      exclude_rtb = snat_policy.value["exclude_rtb"]
      # interface - (optional) is a type of string
      interface = snat_policy.value["interface"]
      # mark - (optional) is a type of string
      mark = snat_policy.value["mark"]
      # protocol - (optional) is a type of string
      protocol = snat_policy.value["protocol"]
      # snat_ips - (optional) is a type of string
      snat_ips = snat_policy.value["snat_ips"]
      # snat_port - (optional) is a type of string
      snat_port = snat_policy.value["snat_port"]
      # src_cidr - (optional) is a type of string
      src_cidr = snat_policy.value["src_cidr"]
      # src_port - (optional) is a type of string
      src_port = snat_policy.value["src_port"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = aviatrix_gateway_snat.this.id
}

output "this" {
  value = aviatrix_gateway_snat.this
}
```

[top](#index)