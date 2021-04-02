# oci_core_private_ip

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_private_ip" {
  source = "./modules/oci/r/oci_core_private_ip"

  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # hostname_label - (optional) is a type of string
  hostname_label = null
  # ip_address - (optional) is a type of string
  ip_address = null
  # vlan_id - (optional) is a type of string
  vlan_id = null
  # vnic_id - (optional) is a type of string
  vnic_id = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "hostname_label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_address" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vlan_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vnic_id" {
  description = "(optional)"
  type        = string
  default     = null
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
```

[top](#index)

### Resource

```terraform
resource "oci_core_private_ip" "this" {
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  hostname_label = var.hostname_label
  ip_address     = var.ip_address
  vlan_id        = var.vlan_id
  vnic_id        = var.vnic_id

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "availability_domain" {
  description = "returns a string"
  value       = oci_core_private_ip.this.availability_domain
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_core_private_ip.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_private_ip.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_private_ip.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_private_ip.this.freeform_tags
}

output "hostname_label" {
  description = "returns a string"
  value       = oci_core_private_ip.this.hostname_label
}

output "id" {
  description = "returns a string"
  value       = oci_core_private_ip.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = oci_core_private_ip.this.ip_address
}

output "is_primary" {
  description = "returns a bool"
  value       = oci_core_private_ip.this.is_primary
}

output "subnet_id" {
  description = "returns a string"
  value       = oci_core_private_ip.this.subnet_id
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_private_ip.this.time_created
}

output "vlan_id" {
  description = "returns a string"
  value       = oci_core_private_ip.this.vlan_id
}

output "vnic_id" {
  description = "returns a string"
  value       = oci_core_private_ip.this.vnic_id
}

output "this" {
  value = oci_core_private_ip.this
}
```

[top](#index)