# oci_database_vm_cluster_network

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_vm_cluster_network" {
  source = "./modules/oci/r/oci_database_vm_cluster_network"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # dns - (optional) is a type of list of string
  dns = []
  # exadata_infrastructure_id - (required) is a type of string
  exadata_infrastructure_id = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # ntp - (optional) is a type of list of string
  ntp = []
  # validate_vm_cluster_network - (optional) is a type of bool
  validate_vm_cluster_network = null

  scans = [{
    hostname = null
    ips      = []
    port     = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]

  vm_networks = [{
    domain_name  = null
    gateway      = null
    netmask      = null
    network_type = null
    nodes = [{
      hostname     = null
      ip           = null
      vip          = null
      vip_hostname = null
    }]
    vlan_id = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "dns" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "exadata_infrastructure_id" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "ntp" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "validate_vm_cluster_network" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "scans" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      hostname = string
      ips      = list(string)
      port     = number
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}

variable "vm_networks" {
  description = "nested block: NestingSet, min items: 1, max items: 0"
  type = set(object(
    {
      domain_name  = string
      gateway      = string
      netmask      = string
      network_type = string
      nodes = set(object(
        {
          hostname     = string
          ip           = string
          vip          = string
          vip_hostname = string
        }
      ))
      vlan_id = string
    }
  ))
}
```

[top](#index)

### Resource

```terraform
resource "oci_database_vm_cluster_network" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # defined_tags - (optional) is a type of map of string
  defined_tags = var.defined_tags
  # display_name - (required) is a type of string
  display_name = var.display_name
  # dns - (optional) is a type of list of string
  dns = var.dns
  # exadata_infrastructure_id - (required) is a type of string
  exadata_infrastructure_id = var.exadata_infrastructure_id
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = var.freeform_tags
  # ntp - (optional) is a type of list of string
  ntp = var.ntp
  # validate_vm_cluster_network - (optional) is a type of bool
  validate_vm_cluster_network = var.validate_vm_cluster_network

  dynamic "scans" {
    for_each = var.scans
    content {
      # hostname - (required) is a type of string
      hostname = scans.value["hostname"]
      # ips - (required) is a type of list of string
      ips = scans.value["ips"]
      # port - (required) is a type of number
      port = scans.value["port"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

  dynamic "vm_networks" {
    for_each = var.vm_networks
    content {
      # domain_name - (required) is a type of string
      domain_name = vm_networks.value["domain_name"]
      # gateway - (required) is a type of string
      gateway = vm_networks.value["gateway"]
      # netmask - (required) is a type of string
      netmask = vm_networks.value["netmask"]
      # network_type - (required) is a type of string
      network_type = vm_networks.value["network_type"]
      # vlan_id - (required) is a type of string
      vlan_id = vm_networks.value["vlan_id"]

      dynamic "nodes" {
        for_each = vm_networks.value.nodes
        content {
          # hostname - (required) is a type of string
          hostname = nodes.value["hostname"]
          # ip - (required) is a type of string
          ip = nodes.value["ip"]
          # vip - (optional) is a type of string
          vip = nodes.value["vip"]
          # vip_hostname - (optional) is a type of string
          vip_hostname = nodes.value["vip_hostname"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_database_vm_cluster_network.this.defined_tags
}

output "dns" {
  description = "returns a list of string"
  value       = oci_database_vm_cluster_network.this.dns
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_database_vm_cluster_network.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_database_vm_cluster_network.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_database_vm_cluster_network.this.lifecycle_details
}

output "ntp" {
  description = "returns a list of string"
  value       = oci_database_vm_cluster_network.this.ntp
}

output "state" {
  description = "returns a string"
  value       = oci_database_vm_cluster_network.this.state
}

output "time_created" {
  description = "returns a string"
  value       = oci_database_vm_cluster_network.this.time_created
}

output "vm_cluster_id" {
  description = "returns a string"
  value       = oci_database_vm_cluster_network.this.vm_cluster_id
}

output "this" {
  value = oci_database_vm_cluster_network.this
}
```

[top](#index)