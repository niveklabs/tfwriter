# oci_dataintegration_workspace

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
module "oci_dataintegration_workspace" {
  source = "./modules/oci/r/oci_dataintegration_workspace"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # dns_server_ip - (optional) is a type of string
  dns_server_ip = null
  # dns_server_zone - (optional) is a type of string
  dns_server_zone = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_force_operation - (optional) is a type of bool
  is_force_operation = null
  # is_private_network_enabled - (optional) is a type of bool
  is_private_network_enabled = null
  # quiesce_timeout - (optional) is a type of number
  quiesce_timeout = null
  # subnet_id - (optional) is a type of string
  subnet_id = null
  # vcn_id - (optional) is a type of string
  vcn_id = null

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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "dns_server_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dns_server_zone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_force_operation" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_private_network_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "quiesce_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "subnet_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vcn_id" {
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
resource "oci_dataintegration_workspace" "this" {
  compartment_id             = var.compartment_id
  defined_tags               = var.defined_tags
  description                = var.description
  display_name               = var.display_name
  dns_server_ip              = var.dns_server_ip
  dns_server_zone            = var.dns_server_zone
  freeform_tags              = var.freeform_tags
  is_force_operation         = var.is_force_operation
  is_private_network_enabled = var.is_private_network_enabled
  quiesce_timeout            = var.quiesce_timeout
  subnet_id                  = var.subnet_id
  vcn_id                     = var.vcn_id

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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_dataintegration_workspace.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_dataintegration_workspace.this.description
}

output "dns_server_ip" {
  description = "returns a string"
  value       = oci_dataintegration_workspace.this.dns_server_ip
}

output "dns_server_zone" {
  description = "returns a string"
  value       = oci_dataintegration_workspace.this.dns_server_zone
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_dataintegration_workspace.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_dataintegration_workspace.this.id
}

output "is_private_network_enabled" {
  description = "returns a bool"
  value       = oci_dataintegration_workspace.this.is_private_network_enabled
}

output "state" {
  description = "returns a string"
  value       = oci_dataintegration_workspace.this.state
}

output "state_message" {
  description = "returns a string"
  value       = oci_dataintegration_workspace.this.state_message
}

output "subnet_id" {
  description = "returns a string"
  value       = oci_dataintegration_workspace.this.subnet_id
}

output "time_created" {
  description = "returns a string"
  value       = oci_dataintegration_workspace.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_dataintegration_workspace.this.time_updated
}

output "vcn_id" {
  description = "returns a string"
  value       = oci_dataintegration_workspace.this.vcn_id
}

output "this" {
  value = oci_dataintegration_workspace.this
}
```

[top](#index)