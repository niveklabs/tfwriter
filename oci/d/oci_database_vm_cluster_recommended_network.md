# oci_database_vm_cluster_recommended_network

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_database_vm_cluster_recommended_network" {
  source = "./modules/oci/d/oci_database_vm_cluster_recommended_network"

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

  networks = [{
    cidr         = null
    domain       = null
    gateway      = null
    netmask      = null
    network_type = null
    prefix       = null
    vlan_id      = null
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

variable "networks" {
  description = "nested block: NestingList, min items: 1, max items: 0"
  type = set(object(
    {
      cidr         = string
      domain       = string
      gateway      = string
      netmask      = string
      network_type = string
      prefix       = string
      vlan_id      = string
    }
  ))
}
```

[top](#index)

### Datasource

```terraform
data "oci_database_vm_cluster_recommended_network" "this" {
  compartment_id            = var.compartment_id
  defined_tags              = var.defined_tags
  display_name              = var.display_name
  dns                       = var.dns
  exadata_infrastructure_id = var.exadata_infrastructure_id
  freeform_tags             = var.freeform_tags
  ntp                       = var.ntp

  dynamic "networks" {
    for_each = var.networks
    content {
      cidr         = networks.value["cidr"]
      domain       = networks.value["domain"]
      gateway      = networks.value["gateway"]
      netmask      = networks.value["netmask"]
      network_type = networks.value["network_type"]
      prefix       = networks.value["prefix"]
      vlan_id      = networks.value["vlan_id"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_database_vm_cluster_recommended_network.this.defined_tags
}

output "dns" {
  description = "returns a list of string"
  value       = data.oci_database_vm_cluster_recommended_network.this.dns
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_database_vm_cluster_recommended_network.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_vm_cluster_recommended_network.this.id
}

output "ntp" {
  description = "returns a list of string"
  value       = data.oci_database_vm_cluster_recommended_network.this.ntp
}

output "scans" {
  description = "returns a list of object"
  value       = data.oci_database_vm_cluster_recommended_network.this.scans
}

output "vm_networks" {
  description = "returns a list of object"
  value       = data.oci_database_vm_cluster_recommended_network.this.vm_networks
}

output "this" {
  value = oci_database_vm_cluster_recommended_network.this
}
```

[top](#index)