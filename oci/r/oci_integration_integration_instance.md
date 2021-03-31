# oci_integration_integration_instance

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
module "oci_integration_integration_instance" {
  source = "./modules/oci/r/oci_integration_integration_instance"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # consumption_model - (optional) is a type of string
  consumption_model = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # idcs_at - (optional) is a type of string
  idcs_at = null
  # integration_instance_type - (required) is a type of string
  integration_instance_type = null
  # is_byol - (required) is a type of bool
  is_byol = null
  # is_file_server_enabled - (optional) is a type of bool
  is_file_server_enabled = null
  # is_visual_builder_enabled - (optional) is a type of bool
  is_visual_builder_enabled = null
  # message_packs - (required) is a type of number
  message_packs = null
  # state - (optional) is a type of string
  state = null

  alternate_custom_endpoints = [{
    certificate_secret_id      = null
    certificate_secret_version = null
    hostname                   = null
  }]

  custom_endpoint = [{
    certificate_secret_id      = null
    certificate_secret_version = null
    hostname                   = null
  }]

  network_endpoint_details = [{
    allowlisted_http_ips = []
    allowlisted_http_vcns = [{
      allowlisted_ips = []
      id              = null
    }]
    is_integration_vcn_allowlisted = null
    network_endpoint_type          = null
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

variable "consumption_model" {
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
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "idcs_at" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "integration_instance_type" {
  description = "(required)"
  type        = string
}

variable "is_byol" {
  description = "(required)"
  type        = bool
}

variable "is_file_server_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_visual_builder_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "message_packs" {
  description = "(required)"
  type        = number
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "alternate_custom_endpoints" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      certificate_secret_id      = string
      certificate_secret_version = number
      hostname                   = string
    }
  ))
  default = []
}

variable "custom_endpoint" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      certificate_secret_id      = string
      certificate_secret_version = number
      hostname                   = string
    }
  ))
  default = []
}

variable "network_endpoint_details" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      allowlisted_http_ips = set(string)
      allowlisted_http_vcns = set(object(
        {
          allowlisted_ips = set(string)
          id              = string
        }
      ))
      is_integration_vcn_allowlisted = bool
      network_endpoint_type          = string
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
resource "oci_integration_integration_instance" "this" {
  compartment_id            = var.compartment_id
  consumption_model         = var.consumption_model
  defined_tags              = var.defined_tags
  display_name              = var.display_name
  freeform_tags             = var.freeform_tags
  idcs_at                   = var.idcs_at
  integration_instance_type = var.integration_instance_type
  is_byol                   = var.is_byol
  is_file_server_enabled    = var.is_file_server_enabled
  is_visual_builder_enabled = var.is_visual_builder_enabled
  message_packs             = var.message_packs
  state                     = var.state

  dynamic "alternate_custom_endpoints" {
    for_each = var.alternate_custom_endpoints
    content {
      certificate_secret_id = alternate_custom_endpoints.value["certificate_secret_id"]
      hostname              = alternate_custom_endpoints.value["hostname"]
    }
  }

  dynamic "custom_endpoint" {
    for_each = var.custom_endpoint
    content {
      certificate_secret_id = custom_endpoint.value["certificate_secret_id"]
      hostname              = custom_endpoint.value["hostname"]
    }
  }

  dynamic "network_endpoint_details" {
    for_each = var.network_endpoint_details
    content {
      allowlisted_http_ips           = network_endpoint_details.value["allowlisted_http_ips"]
      is_integration_vcn_allowlisted = network_endpoint_details.value["is_integration_vcn_allowlisted"]
      network_endpoint_type          = network_endpoint_details.value["network_endpoint_type"]

      dynamic "allowlisted_http_vcns" {
        for_each = network_endpoint_details.value.allowlisted_http_vcns
        content {
          allowlisted_ips = allowlisted_http_vcns.value["allowlisted_ips"]
          id              = allowlisted_http_vcns.value["id"]
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
output "consumption_model" {
  description = "returns a string"
  value       = oci_integration_integration_instance.this.consumption_model
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_integration_integration_instance.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_integration_integration_instance.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_integration_integration_instance.this.id
}

output "instance_url" {
  description = "returns a string"
  value       = oci_integration_integration_instance.this.instance_url
}

output "is_file_server_enabled" {
  description = "returns a bool"
  value       = oci_integration_integration_instance.this.is_file_server_enabled
}

output "is_visual_builder_enabled" {
  description = "returns a bool"
  value       = oci_integration_integration_instance.this.is_visual_builder_enabled
}

output "state" {
  description = "returns a string"
  value       = oci_integration_integration_instance.this.state
}

output "state_message" {
  description = "returns a string"
  value       = oci_integration_integration_instance.this.state_message
}

output "time_created" {
  description = "returns a string"
  value       = oci_integration_integration_instance.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_integration_integration_instance.this.time_updated
}

output "this" {
  value = oci_integration_integration_instance.this
}
```

[top](#index)