# bigip_ltm_snat

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
    bigip = ">= 1.8.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_ltm_snat" {
  source = "./modules/bigip/r/bigip_ltm_snat"

  # autolasthop - (optional) is a type of string
  autolasthop = null
  # full_path - (optional) is a type of string
  full_path = null
  # mirror - (optional) is a type of string
  mirror = null
  # name - (required) is a type of string
  name = null
  # partition - (optional) is a type of string
  partition = null
  # snatpool - (optional) is a type of string
  snatpool = null
  # sourceport - (optional) is a type of string
  sourceport = null
  # translation - (optional) is a type of string
  translation = null
  # vlans - (optional) is a type of set of string
  vlans = []
  # vlansdisabled - (optional) is a type of bool
  vlansdisabled = null

  origins = [{
    app_service = null
    name        = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "autolasthop" {
  description = "(optional) - Specifies whether to automatically map last hop for pools or not. The default is to use next level's defaul"
  type        = string
  default     = null
}

variable "full_path" {
  description = "(optional) - Fullpath "
  type        = string
  default     = null
}

variable "mirror" {
  description = "(optional) - Enables or disables mirroring of SNAT connections."
  type        = string
  default     = null
}

variable "name" {
  description = "(required) - Snat list Name"
  type        = string
}

variable "partition" {
  description = "(optional) - Which partition on BIG-IP"
  type        = string
  default     = null
}

variable "snatpool" {
  description = "(optional) - Specifies the name of a SNAT pool. You can only use this option when automap and translation are not used"
  type        = string
  default     = null
}

variable "sourceport" {
  description = "(optional) - Specifies whether the system preserves the source port of the connection. "
  type        = string
  default     = null
}

variable "translation" {
  description = "(optional) - Specifies the name of a translated IP address."
  type        = string
  default     = null
}

variable "vlans" {
  description = "(optional) - Vlans or Vlan list"
  type        = set(string)
  default     = null
}

variable "vlansdisabled" {
  description = "(optional) - Disables the SNAT on all VLANs."
  type        = bool
  default     = null
}

variable "origins" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      app_service = string
      name        = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "bigip_ltm_snat" "this" {
  autolasthop   = var.autolasthop
  full_path     = var.full_path
  mirror        = var.mirror
  name          = var.name
  partition     = var.partition
  snatpool      = var.snatpool
  sourceport    = var.sourceport
  translation   = var.translation
  vlans         = var.vlans
  vlansdisabled = var.vlansdisabled

  dynamic "origins" {
    for_each = var.origins
    content {
      app_service = origins.value["app_service"]
      name        = origins.value["name"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = bigip_ltm_snat.this.id
}

output "this" {
  value = bigip_ltm_snat.this
}
```

[top](#index)