# vcd_network_direct

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
module "vcd_network_direct" {
  source = "./modules/vcd/d/vcd_network_direct"

  # name - (optional) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null

  filter = [{
    ip = null
    metadata = [{
      is_system      = null
      key            = null
      type           = null
      use_api_search = null
      value          = null
    }]
    name_regex = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - A unique name for this network (optional if 'filter' is used)"
  type        = string
  default     = null
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "vdc" {
  description = "(optional) - The name of VDC to use, optional if defined at provider level"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ip = string
      metadata = list(object(
        {
          is_system      = bool
          key            = string
          type           = string
          use_api_search = bool
          value          = string
        }
      ))
      name_regex = string
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "vcd_network_direct" "this" {
  # name - (optional) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "filter" {
    for_each = var.filter
    content {
      # ip - (optional) is a type of string
      ip = filter.value["ip"]
      # name_regex - (optional) is a type of string
      name_regex = filter.value["name_regex"]

      dynamic "metadata" {
        for_each = filter.value.metadata
        content {
          # is_system - (optional) is a type of bool
          is_system = metadata.value["is_system"]
          # key - (required) is a type of string
          key = metadata.value["key"]
          # type - (optional) is a type of string
          type = metadata.value["type"]
          # use_api_search - (optional) is a type of bool
          use_api_search = metadata.value["use_api_search"]
          # value - (required) is a type of string
          value = metadata.value["value"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.vcd_network_direct.this.description
}

output "external_network" {
  description = "returns a string"
  value       = data.vcd_network_direct.this.external_network
}

output "external_network_dns1" {
  description = "returns a string"
  value       = data.vcd_network_direct.this.external_network_dns1
}

output "external_network_dns2" {
  description = "returns a string"
  value       = data.vcd_network_direct.this.external_network_dns2
}

output "external_network_dns_suffix" {
  description = "returns a string"
  value       = data.vcd_network_direct.this.external_network_dns_suffix
}

output "external_network_gateway" {
  description = "returns a string"
  value       = data.vcd_network_direct.this.external_network_gateway
}

output "external_network_netmask" {
  description = "returns a string"
  value       = data.vcd_network_direct.this.external_network_netmask
}

output "href" {
  description = "returns a string"
  value       = data.vcd_network_direct.this.href
}

output "id" {
  description = "returns a string"
  value       = data.vcd_network_direct.this.id
}

output "shared" {
  description = "returns a bool"
  value       = data.vcd_network_direct.this.shared
}

output "this" {
  value = vcd_network_direct.this
}
```

[top](#index)