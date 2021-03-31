# mso_schema_site_vrf_region

[back](../mso.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    mso = ">= 0.1.5"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "mso_schema_site_vrf_region" {
  source = "./modules/mso/r/mso_schema_site_vrf_region"

  # hub_network - (optional) is a type of map of string
  hub_network = {}
  # hub_network_enable - (optional) is a type of bool
  hub_network_enable = null
  # region_name - (required) is a type of string
  region_name = null
  # schema_id - (required) is a type of string
  schema_id = null
  # site_id - (required) is a type of string
  site_id = null
  # template_name - (required) is a type of string
  template_name = null
  # vpn_gateway - (optional) is a type of bool
  vpn_gateway = null
  # vrf_name - (required) is a type of string
  vrf_name = null

  cidr = [{
    cidr_ip = null
    primary = null
    subnet = [{
      ip    = null
      usage = null
      zone  = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "hub_network" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "hub_network_enable" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "region_name" {
  description = "(required)"
  type        = string
}

variable "schema_id" {
  description = "(required)"
  type        = string
}

variable "site_id" {
  description = "(required)"
  type        = string
}

variable "template_name" {
  description = "(required)"
  type        = string
}

variable "vpn_gateway" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vrf_name" {
  description = "(required)"
  type        = string
}

variable "cidr" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      cidr_ip = string
      primary = bool
      subnet = list(object(
        {
          ip    = string
          usage = string
          zone  = string
        }
      ))
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "mso_schema_site_vrf_region" "this" {
  hub_network        = var.hub_network
  hub_network_enable = var.hub_network_enable
  region_name        = var.region_name
  schema_id          = var.schema_id
  site_id            = var.site_id
  template_name      = var.template_name
  vpn_gateway        = var.vpn_gateway
  vrf_name           = var.vrf_name

  dynamic "cidr" {
    for_each = var.cidr
    content {
      cidr_ip = cidr.value["cidr_ip"]
      primary = cidr.value["primary"]

      dynamic "subnet" {
        for_each = cidr.value.subnet
        content {
          ip    = subnet.value["ip"]
          usage = subnet.value["usage"]
          zone  = subnet.value["zone"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "hub_network" {
  description = "returns a map of string"
  value       = mso_schema_site_vrf_region.this.hub_network
}

output "hub_network_enable" {
  description = "returns a bool"
  value       = mso_schema_site_vrf_region.this.hub_network_enable
}

output "id" {
  description = "returns a string"
  value       = mso_schema_site_vrf_region.this.id
}

output "vpn_gateway" {
  description = "returns a bool"
  value       = mso_schema_site_vrf_region.this.vpn_gateway
}

output "this" {
  value = mso_schema_site_vrf_region.this
}
```

[top](#index)