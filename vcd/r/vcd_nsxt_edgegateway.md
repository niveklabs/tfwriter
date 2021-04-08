# vcd_nsxt_edgegateway

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
module "vcd_nsxt_edgegateway" {
  source = "./modules/vcd/r/vcd_nsxt_edgegateway"

  # dedicate_external_network - (optional) is a type of bool
  dedicate_external_network = null
  # description - (optional) is a type of string
  description = null
  # edge_cluster_id - (optional) is a type of string
  edge_cluster_id = null
  # external_network_id - (required) is a type of string
  external_network_id = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # vdc - (optional) is a type of string
  vdc = null

  subnet = [{
    allocated_ips = [{
      end_address   = null
      start_address = null
    }]
    gateway       = null
    prefix_length = null
    primary_ip    = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "dedicate_external_network" {
  description = "(optional) - Dedicating the External Network will enable Route Advertisement for this Edge Gateway."
  type        = bool
  default     = null
}

variable "description" {
  description = "(optional) - Edge Gateway description"
  type        = string
  default     = null
}

variable "edge_cluster_id" {
  description = "(optional) - Select specific NSX-T Edge Cluster. Will be inherited from external network if not specified"
  type        = string
  default     = null
}

variable "external_network_id" {
  description = "(required) - External network ID"
  type        = string
}

variable "name" {
  description = "(required) - Edge Gateway name"
  type        = string
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

variable "subnet" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      allocated_ips = set(object(
        {
          end_address   = string
          start_address = string
        }
      ))
      gateway       = string
      prefix_length = number
      primary_ip    = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "vcd_nsxt_edgegateway" "this" {
  # dedicate_external_network - (optional) is a type of bool
  dedicate_external_network = var.dedicate_external_network
  # description - (optional) is a type of string
  description = var.description
  # edge_cluster_id - (optional) is a type of string
  edge_cluster_id = var.edge_cluster_id
  # external_network_id - (required) is a type of string
  external_network_id = var.external_network_id
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # vdc - (optional) is a type of string
  vdc = var.vdc

  dynamic "subnet" {
    for_each = var.subnet
    content {
      # gateway - (required) is a type of string
      gateway = subnet.value["gateway"]
      # prefix_length - (required) is a type of number
      prefix_length = subnet.value["prefix_length"]
      # primary_ip - (optional) is a type of string
      primary_ip = subnet.value["primary_ip"]

      dynamic "allocated_ips" {
        for_each = subnet.value.allocated_ips
        content {
          # end_address - (required) is a type of string
          end_address = allocated_ips.value["end_address"]
          # start_address - (required) is a type of string
          start_address = allocated_ips.value["start_address"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "edge_cluster_id" {
  description = "returns a string"
  value       = vcd_nsxt_edgegateway.this.edge_cluster_id
}

output "id" {
  description = "returns a string"
  value       = vcd_nsxt_edgegateway.this.id
}

output "primary_ip" {
  description = "returns a string"
  value       = vcd_nsxt_edgegateway.this.primary_ip
}

output "this" {
  value = vcd_nsxt_edgegateway.this
}
```

[top](#index)