# oci_core_vnic_attachment

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_core_vnic_attachment" {
  source = "./modules/oci/r/oci_core_vnic_attachment"

  # display_name - (optional) is a type of string
  display_name = null
  # instance_id - (required) is a type of string
  instance_id = null
  # nic_index - (optional) is a type of number
  nic_index = null

  create_vnic_details = [{
    assign_public_ip       = null
    defined_tags           = {}
    display_name           = null
    freeform_tags          = {}
    hostname_label         = null
    nsg_ids                = []
    private_ip             = null
    skip_source_dest_check = null
    subnet_id              = null
    vlan_id                = null
  }]

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
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_id" {
  description = "(required)"
  type        = string
}

variable "nic_index" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "create_vnic_details" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      assign_public_ip       = string
      defined_tags           = map(string)
      display_name           = string
      freeform_tags          = map(string)
      hostname_label         = string
      nsg_ids                = set(string)
      private_ip             = string
      skip_source_dest_check = bool
      subnet_id              = string
      vlan_id                = string
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
```

[top](#index)

### Resource

```terraform
resource "oci_core_vnic_attachment" "this" {
  display_name = var.display_name
  instance_id  = var.instance_id
  nic_index    = var.nic_index

  dynamic "create_vnic_details" {
    for_each = var.create_vnic_details
    content {
      assign_public_ip       = create_vnic_details.value["assign_public_ip"]
      defined_tags           = create_vnic_details.value["defined_tags"]
      display_name           = create_vnic_details.value["display_name"]
      freeform_tags          = create_vnic_details.value["freeform_tags"]
      hostname_label         = create_vnic_details.value["hostname_label"]
      nsg_ids                = create_vnic_details.value["nsg_ids"]
      private_ip             = create_vnic_details.value["private_ip"]
      skip_source_dest_check = create_vnic_details.value["skip_source_dest_check"]
      subnet_id              = create_vnic_details.value["subnet_id"]
      vlan_id                = create_vnic_details.value["vlan_id"]
    }
  }

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
  value       = oci_core_vnic_attachment.this.availability_domain
}

output "compartment_id" {
  description = "returns a string"
  value       = oci_core_vnic_attachment.this.compartment_id
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_vnic_attachment.this.display_name
}

output "id" {
  description = "returns a string"
  value       = oci_core_vnic_attachment.this.id
}

output "nic_index" {
  description = "returns a number"
  value       = oci_core_vnic_attachment.this.nic_index
}

output "state" {
  description = "returns a string"
  value       = oci_core_vnic_attachment.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = oci_core_vnic_attachment.this.subnet_id
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_vnic_attachment.this.time_created
}

output "vlan_id" {
  description = "returns a string"
  value       = oci_core_vnic_attachment.this.vlan_id
}

output "vlan_tag" {
  description = "returns a number"
  value       = oci_core_vnic_attachment.this.vlan_tag
}

output "vnic_id" {
  description = "returns a string"
  value       = oci_core_vnic_attachment.this.vnic_id
}

output "this" {
  value = oci_core_vnic_attachment.this
}
```

[top](#index)