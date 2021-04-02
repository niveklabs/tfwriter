# oci_core_instance_configuration

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
module "oci_core_instance_configuration" {
  source = null

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (optional) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # instance_id - (optional) is a type of string
  instance_id = null
  # source - (optional) is a type of string

  instance_details = [{
    block_volumes = [{
      attach_details = [{
        device                              = null
        display_name                        = null
        is_pv_encryption_in_transit_enabled = null
        is_read_only                        = null
        is_shareable                        = null
        type                                = null
        use_chap                            = null
      }]
      create_details = [{
        availability_domain = null
        backup_policy_id    = null
        compartment_id      = null
        defined_tags        = {}
        display_name        = null
        freeform_tags       = {}
        kms_key_id          = null
        size_in_gbs         = null
        source_details = [{
          id   = null
          type = null
        }]
        vpus_per_gb = null
      }]
      volume_id = null
    }]
    instance_type = null
    launch_details = [{
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
      availability_domain     = null
      capacity_reservation_id = null
      compartment_id          = null
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
      }]
      dedicated_vm_host_id = null
      defined_tags         = {}
      display_name         = null
      extended_metadata    = {}
      fault_domain         = null
      freeform_tags        = {}
      instance_options = [{
        are_legacy_imds_endpoints_disabled = null
      }]
      ipxe_script                         = null
      is_pv_encryption_in_transit_enabled = null
      launch_mode                         = null
      launch_options = [{
        boot_volume_type                    = null
        firmware                            = null
        is_consistent_volume_naming_enabled = null
        is_pv_encryption_in_transit_enabled = null
        network_type                        = null
        remote_data_volume_type             = null
      }]
      metadata = {}
      platform_config = [{
        numa_nodes_per_socket = null
        type                  = null
      }]
      preferred_maintenance_action = null
      shape                        = null
      shape_config = [{
        memory_in_gbs = null
        ocpus         = null
      }]
      source_details = [{
        boot_volume_id          = null
        boot_volume_size_in_gbs = null
        image_id                = null
        source_type             = null
      }]
    }]
    secondary_vnics = [{
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
      }]
      display_name = null
      nic_index    = null
    }]
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
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "instance_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      block_volumes = list(object(
        {
          attach_details = list(object(
            {
              device                              = string
              display_name                        = string
              is_pv_encryption_in_transit_enabled = bool
              is_read_only                        = bool
              is_shareable                        = bool
              type                                = string
              use_chap                            = bool
            }
          ))
          create_details = list(object(
            {
              availability_domain = string
              backup_policy_id    = string
              compartment_id      = string
              defined_tags        = map(string)
              display_name        = string
              freeform_tags       = map(string)
              kms_key_id          = string
              size_in_gbs         = string
              source_details = list(object(
                {
                  id   = string
                  type = string
                }
              ))
              vpus_per_gb = string
            }
          ))
          volume_id = string
        }
      ))
      instance_type = string
      launch_details = list(object(
        {
          agent_config = list(object(
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
          availability_config = list(object(
            {
              recovery_action = string
            }
          ))
          availability_domain     = string
          capacity_reservation_id = string
          compartment_id          = string
          create_vnic_details = list(object(
            {
              assign_public_ip       = bool
              defined_tags           = map(string)
              display_name           = string
              freeform_tags          = map(string)
              hostname_label         = string
              nsg_ids                = set(string)
              private_ip             = string
              skip_source_dest_check = bool
              subnet_id              = string
            }
          ))
          dedicated_vm_host_id = string
          defined_tags         = map(string)
          display_name         = string
          extended_metadata    = map(string)
          fault_domain         = string
          freeform_tags        = map(string)
          instance_options = list(object(
            {
              are_legacy_imds_endpoints_disabled = bool
            }
          ))
          ipxe_script                         = string
          is_pv_encryption_in_transit_enabled = bool
          launch_mode                         = string
          launch_options = list(object(
            {
              boot_volume_type                    = string
              firmware                            = string
              is_consistent_volume_naming_enabled = bool
              is_pv_encryption_in_transit_enabled = bool
              network_type                        = string
              remote_data_volume_type             = string
            }
          ))
          metadata = map(string)
          platform_config = list(object(
            {
              numa_nodes_per_socket = string
              type                  = string
            }
          ))
          preferred_maintenance_action = string
          shape                        = string
          shape_config = list(object(
            {
              memory_in_gbs = number
              ocpus         = number
            }
          ))
          source_details = list(object(
            {
              boot_volume_id          = string
              boot_volume_size_in_gbs = string
              image_id                = string
              source_type             = string
            }
          ))
        }
      ))
      secondary_vnics = list(object(
        {
          create_vnic_details = list(object(
            {
              assign_public_ip       = bool
              defined_tags           = map(string)
              display_name           = string
              freeform_tags          = map(string)
              hostname_label         = string
              nsg_ids                = set(string)
              private_ip             = string
              skip_source_dest_check = bool
              subnet_id              = string
            }
          ))
          display_name = string
          nic_index    = number
        }
      ))
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
resource "oci_core_instance_configuration" "this" {
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  instance_id    = var.instance_id
  source         = var.source

  dynamic "instance_details" {
    for_each = var.instance_details
    content {
      instance_type = instance_details.value["instance_type"]

      dynamic "block_volumes" {
        for_each = instance_details.value.block_volumes
        content {
          volume_id = block_volumes.value["volume_id"]

          dynamic "attach_details" {
            for_each = block_volumes.value.attach_details
            content {
              device                              = attach_details.value["device"]
              display_name                        = attach_details.value["display_name"]
              is_pv_encryption_in_transit_enabled = attach_details.value["is_pv_encryption_in_transit_enabled"]
              is_read_only                        = attach_details.value["is_read_only"]
              is_shareable                        = attach_details.value["is_shareable"]
              type                                = attach_details.value["type"]
              use_chap                            = attach_details.value["use_chap"]
            }
          }

          dynamic "create_details" {
            for_each = block_volumes.value.create_details
            content {
              availability_domain = create_details.value["availability_domain"]
              backup_policy_id    = create_details.value["backup_policy_id"]
              compartment_id      = create_details.value["compartment_id"]
              defined_tags        = create_details.value["defined_tags"]
              display_name        = create_details.value["display_name"]
              freeform_tags       = create_details.value["freeform_tags"]
              kms_key_id          = create_details.value["kms_key_id"]
              size_in_gbs         = create_details.value["size_in_gbs"]
              vpus_per_gb         = create_details.value["vpus_per_gb"]

              dynamic "source_details" {
                for_each = create_details.value.source_details
                content {
                  id   = source_details.value["id"]
                  type = source_details.value["type"]
                }
              }

            }
          }

        }
      }

      dynamic "launch_details" {
        for_each = instance_details.value.launch_details
        content {
          availability_domain                 = launch_details.value["availability_domain"]
          capacity_reservation_id             = launch_details.value["capacity_reservation_id"]
          compartment_id                      = launch_details.value["compartment_id"]
          dedicated_vm_host_id                = launch_details.value["dedicated_vm_host_id"]
          defined_tags                        = launch_details.value["defined_tags"]
          display_name                        = launch_details.value["display_name"]
          extended_metadata                   = launch_details.value["extended_metadata"]
          fault_domain                        = launch_details.value["fault_domain"]
          freeform_tags                       = launch_details.value["freeform_tags"]
          ipxe_script                         = launch_details.value["ipxe_script"]
          is_pv_encryption_in_transit_enabled = launch_details.value["is_pv_encryption_in_transit_enabled"]
          launch_mode                         = launch_details.value["launch_mode"]
          metadata                            = launch_details.value["metadata"]
          preferred_maintenance_action        = launch_details.value["preferred_maintenance_action"]
          shape                               = launch_details.value["shape"]

          dynamic "agent_config" {
            for_each = launch_details.value.agent_config
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
            for_each = launch_details.value.availability_config
            content {
              recovery_action = availability_config.value["recovery_action"]
            }
          }

          dynamic "create_vnic_details" {
            for_each = launch_details.value.create_vnic_details
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
            }
          }

          dynamic "instance_options" {
            for_each = launch_details.value.instance_options
            content {
              are_legacy_imds_endpoints_disabled = instance_options.value["are_legacy_imds_endpoints_disabled"]
            }
          }

          dynamic "launch_options" {
            for_each = launch_details.value.launch_options
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
            for_each = launch_details.value.platform_config
            content {
              numa_nodes_per_socket = platform_config.value["numa_nodes_per_socket"]
              type                  = platform_config.value["type"]
            }
          }

          dynamic "shape_config" {
            for_each = launch_details.value.shape_config
            content {
              memory_in_gbs = shape_config.value["memory_in_gbs"]
              ocpus         = shape_config.value["ocpus"]
            }
          }

          dynamic "source_details" {
            for_each = launch_details.value.source_details
            content {
              boot_volume_id          = source_details.value["boot_volume_id"]
              boot_volume_size_in_gbs = source_details.value["boot_volume_size_in_gbs"]
              image_id                = source_details.value["image_id"]
              source_type             = source_details.value["source_type"]
            }
          }

        }
      }

      dynamic "secondary_vnics" {
        for_each = instance_details.value.secondary_vnics
        content {
          display_name = secondary_vnics.value["display_name"]
          nic_index    = secondary_vnics.value["nic_index"]

          dynamic "create_vnic_details" {
            for_each = secondary_vnics.value.create_vnic_details
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
            }
          }

        }
      }

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
output "deferred_fields" {
  description = "returns a list of string"
  value       = oci_core_instance_configuration.this.deferred_fields
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_core_instance_configuration.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = oci_core_instance_configuration.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_core_instance_configuration.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_core_instance_configuration.this.id
}

output "instance_id" {
  description = "returns a string"
  value       = oci_core_instance_configuration.this.instance_id
}

output "source" {
  description = "returns a string"
  value       = oci_core_instance_configuration.this.source
}

output "time_created" {
  description = "returns a string"
  value       = oci_core_instance_configuration.this.time_created
}

output "this" {
  value = oci_core_instance_configuration.this
}
```

[top](#index)