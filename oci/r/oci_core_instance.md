# oci_core_instance

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
module "oci_core_instance" {
  source = "./modules/oci/r/oci_core_instance"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # capacity_reservation_id - (optional) is a type of string
  capacity_reservation_id = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # dedicated_vm_host_id - (optional) is a type of string
  dedicated_vm_host_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # extended_metadata - (optional) is a type of map of string
  extended_metadata = {}
  # fault_domain - (optional) is a type of string
  fault_domain = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # hostname_label - (optional) is a type of string
  hostname_label = null
  # image - (optional) is a type of string
  image = null
  # ipxe_script - (optional) is a type of string
  ipxe_script = null
  # is_pv_encryption_in_transit_enabled - (optional) is a type of bool
  is_pv_encryption_in_transit_enabled = null
  # metadata - (optional) is a type of map of string
  metadata = {}
  # preserve_boot_volume - (optional) is a type of bool
  preserve_boot_volume = null
  # shape - (required) is a type of string
  shape = null
  # state - (optional) is a type of string
  state = null
  # subnet_id - (optional) is a type of string
  subnet_id = null

  agent_config = [{
    are_all_plugins_disabled = null
    is_management_disabled   = null
    is_monitoring_disabled   = null
    plugins_config = [{
      desired_state = null
      name          = null
    }]
  }]

  availability_config = [{
    recovery_action = null
  }]

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

  instance_options = [{
    are_legacy_imds_endpoints_disabled = null
  }]

  launch_options = [{
    boot_volume_type                    = null
    firmware                            = null
    is_consistent_volume_naming_enabled = null
    is_pv_encryption_in_transit_enabled = null
    network_type                        = null
    remote_data_volume_type             = null
  }]

  platform_config = [{
    numa_nodes_per_socket = null
    type                  = null
  }]

  shape_config = [{
    gpu_description               = null
    gpus                          = null
    local_disk_description        = null
    local_disks                   = null
    local_disks_total_size_in_gbs = null
    max_vnic_attachments          = null
    memory_in_gbs                 = null
    networking_bandwidth_in_gbps  = null
    ocpus                         = null
    processor_description         = null
  }]

  source_details = [{
    boot_volume_size_in_gbs = null
    kms_key_id              = null
    source_id               = null
    source_type             = null
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
variable "availability_domain" {
  description = "(required)"
  type        = string
}

variable "capacity_reservation_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "dedicated_vm_host_id" {
  description = "(optional)"
  type        = string
  default     = null
}

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

variable "extended_metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "fault_domain" {
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

variable "image" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipxe_script" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_pv_encryption_in_transit_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "metadata" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "preserve_boot_volume" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "shape" {
  description = "(required)"
  type        = string
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "agent_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      are_all_plugins_disabled = bool
      is_management_disabled   = bool
      is_monitoring_disabled   = bool
      plugins_config = list(object(
        {
          desired_state = string
          name          = string
        }
      ))
    }
  ))
  default = []
}

variable "availability_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      recovery_action = string
    }
  ))
  default = []
}

variable "create_vnic_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
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
  default = []
}

variable "instance_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      are_legacy_imds_endpoints_disabled = bool
    }
  ))
  default = []
}

variable "launch_options" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      boot_volume_type                    = string
      firmware                            = string
      is_consistent_volume_naming_enabled = bool
      is_pv_encryption_in_transit_enabled = bool
      network_type                        = string
      remote_data_volume_type             = string
    }
  ))
  default = []
}

variable "platform_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      numa_nodes_per_socket = string
      type                  = string
    }
  ))
  default = []
}

variable "shape_config" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      gpu_description               = string
      gpus                          = number
      local_disk_description        = string
      local_disks                   = number
      local_disks_total_size_in_gbs = number
      max_vnic_attachments          = number
      memory_in_gbs                 = number
      networking_bandwidth_in_gbps  = number
      ocpus                         = number
      processor_description         = string
    }
  ))
  default = []
}

variable "source_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      boot_volume_size_in_gbs = string
      kms_key_id              = string
      source_id               = string
      source_type             = string
    }
  ))
  default = []
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
resource "oci_core_instance" "this" {
  availability_domain                 = var.availability_domain
  capacity_reservation_id             = var.capacity_reservation_id
  compartment_id                      = var.compartment_id
  dedicated_vm_host_id                = var.dedicated_vm_host_id
  defined_tags                        = var.defined_tags
  display_name                        = var.display_name
  extended_metadata                   = var.extended_metadata
  fault_domain                        = var.fault_domain
  freeform_tags                       = var.freeform_tags
  hostname_label                      = var.hostname_label
  image                               = var.image
  ipxe_script                         = var.ipxe_script
  is_pv_encryption_in_transit_enabled = var.is_pv_encryption_in_transit_enabled
  metadata                            = var.metadata
  preserve_boot_volume                = var.preserve_boot_volume
  shape                               = var.shape
  state                               = var.state
  subnet_id                           = var.subnet_id

  dynamic "agent_config" {
    for_each = var.agent_config
    content {
      are_all_plugins_disabled = agent_config.value["are_all_plugins_disabled"]
      is_management_disabled   = agent_config.value["is_management_disabled"]
      is_monitoring_disabled   = agent_config.value["is_monitoring_disabled"]

      dynamic "plugins_config" {
        for_each = agent_config.value.plugins_config
        content {
          desired_state = plugins_config.value["desired_state"]
          name          = plugins_config.value["name"]
        }
      }

    }
  }

  dynamic "availability_config" {
    for_each = var.availability_config
    content {
      recovery_action = availability_config.value["recovery_action"]
    }
  }

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

  dynamic "instance_options" {
    for_each = var.instance_options
    content {
      are_legacy_imds_endpoints_disabled = instance_options.value["are_legacy_imds_endpoints_disabled"]
    }
  }

  dynamic "launch_options" {
    for_each = var.launch_options
    content {
      boot_volume_type                    = launch_options.value["boot_volume_type"]
      firmware                            = launch_options.value["firmware"]
      is_consistent_volume_naming_enabled = launch_options.value["is_consistent_volume_naming_enabled"]
      is_pv_encryption_in_transit_enabled = launch_options.value["is_pv_encryption_in_transit_enabled"]
      network_type                        = launch_options.value["network_type"]
      remote_data_volume_type             = launch_options.value["remote_data_volume_type"]
    }
  }

  dynamic "platform_config" {
    for_each = var.platform_config
    content {
      numa_nodes_per_socket = platform_config.value["numa_nodes_per_socket"]
      type                  = platform_config.value["type"]
    }
  }

  dynamic "shape_config" {
    for_each = var.shape_config
    content {
      memory_in_gbs = shape_config.value["memory_in_gbs"]
      ocpus         = shape_config.value["ocpus"]
    }
  }

  dynamic "source_details" {
    for_each = var.source_details
    content {
      boot_volume_size_in_gbs = source_details.value["boot_volume_size_in_gbs"]
      kms_key_id              = source_details.value["kms_key_id"]
      source_id               = source_details.value["source_id"]
      source_type             = source_details.value["source_type"]
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
output "boot_volume_id" {
  description = "returns a string"
  value       = oci_core_instance.this.boot_volume_id
}

output "capacity_reservation_id" {
  description = "returns a string"
  value       = oci_core_instance.this.capacity_reservation_id
}

output "dedicated_vm_host_id" {
  description = "returns a string"
  value       = oci_core_instance.this.dedicated_vm_host_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_instance.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_instance.this.display_name
}

output "fault_domain" {
  description = "returns a string"
  value       = oci_core_instance.this.fault_domain
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_instance.this.freeform_tags
}

output "hostname_label" {
  description = "returns a string"
  value       = oci_core_instance.this.hostname_label
}

output "id" {
  description = "returns a string"
  value       = oci_core_instance.this.id
}

output "image" {
  description = "returns a string"
  value       = oci_core_instance.this.image
}

output "ipxe_script" {
  description = "returns a string"
  value       = oci_core_instance.this.ipxe_script
}

output "is_pv_encryption_in_transit_enabled" {
  description = "returns a bool"
  value       = oci_core_instance.this.is_pv_encryption_in_transit_enabled
}

output "launch_mode" {
  description = "returns a string"
  value       = oci_core_instance.this.launch_mode
}

output "private_ip" {
  description = "returns a string"
  value       = oci_core_instance.this.private_ip
}

output "public_ip" {
  description = "returns a string"
  value       = oci_core_instance.this.public_ip
}

output "region" {
  description = "returns a string"
  value       = oci_core_instance.this.region
}

output "state" {
  description = "returns a string"
  value       = oci_core_instance.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = oci_core_instance.this.subnet_id
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_core_instance.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_instance.this.time_created
}

output "time_maintenance_reboot_due" {
  description = "returns a string"
  value       = oci_core_instance.this.time_maintenance_reboot_due
}

output "this" {
  value = oci_core_instance.this
}
```

[top](#index)