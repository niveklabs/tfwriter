# oci_golden_gate_deployment

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
module "oci_golden_gate_deployment" {
  source = "./modules/oci/r/oci_golden_gate_deployment"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # cpu_core_count - (required) is a type of number
  cpu_core_count = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # deployment_backup_id - (optional) is a type of string
  deployment_backup_id = null
  # deployment_type - (required) is a type of string
  deployment_type = null
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # fqdn - (optional) is a type of string
  fqdn = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # is_auto_scaling_enabled - (required) is a type of bool
  is_auto_scaling_enabled = null
  # is_public - (optional) is a type of bool
  is_public = null
  # license_model - (required) is a type of string
  license_model = null
  # nsg_ids - (optional) is a type of set of string
  nsg_ids = []
  # subnet_id - (required) is a type of string
  subnet_id = null

  ogg_data = [{
    admin_password  = null
    admin_username  = null
    certificate     = null
    deployment_name = null
    key             = null
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

variable "cpu_core_count" {
  description = "(required)"
  type        = number
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "deployment_backup_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "deployment_type" {
  description = "(required)"
  type        = string
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

variable "fqdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "is_auto_scaling_enabled" {
  description = "(required)"
  type        = bool
}

variable "is_public" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "license_model" {
  description = "(required)"
  type        = string
}

variable "nsg_ids" {
  description = "(optional)"
  type        = set(string)
  default     = null
}

variable "subnet_id" {
  description = "(required)"
  type        = string
}

variable "ogg_data" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      admin_password  = string
      admin_username  = string
      certificate     = string
      deployment_name = string
      key             = string
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
resource "oci_golden_gate_deployment" "this" {
  compartment_id          = var.compartment_id
  cpu_core_count          = var.cpu_core_count
  defined_tags            = var.defined_tags
  deployment_backup_id    = var.deployment_backup_id
  deployment_type         = var.deployment_type
  description             = var.description
  display_name            = var.display_name
  fqdn                    = var.fqdn
  freeform_tags           = var.freeform_tags
  is_auto_scaling_enabled = var.is_auto_scaling_enabled
  is_public               = var.is_public
  license_model           = var.license_model
  nsg_ids                 = var.nsg_ids
  subnet_id               = var.subnet_id

  dynamic "ogg_data" {
    for_each = var.ogg_data
    content {
      admin_password  = ogg_data.value["admin_password"]
      admin_username  = ogg_data.value["admin_username"]
      certificate     = ogg_data.value["certificate"]
      deployment_name = ogg_data.value["deployment_name"]
      key             = ogg_data.value["key"]
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
output "defined_tags" {
  description = "returns a map of string"
  value       = oci_golden_gate_deployment.this.defined_tags
}

output "deployment_backup_id" {
  description = "returns a string"
  value       = oci_golden_gate_deployment.this.deployment_backup_id
}

output "deployment_url" {
  description = "returns a string"
  value       = oci_golden_gate_deployment.this.deployment_url
}

output "description" {
  description = "returns a string"
  value       = oci_golden_gate_deployment.this.description
}

output "fqdn" {
  description = "returns a string"
  value       = oci_golden_gate_deployment.this.fqdn
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_golden_gate_deployment.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_golden_gate_deployment.this.id
}

output "is_healthy" {
  description = "returns a bool"
  value       = oci_golden_gate_deployment.this.is_healthy
}

output "is_latest_version" {
  description = "returns a bool"
  value       = oci_golden_gate_deployment.this.is_latest_version
}

output "is_public" {
  description = "returns a bool"
  value       = oci_golden_gate_deployment.this.is_public
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_golden_gate_deployment.this.lifecycle_details
}

output "nsg_ids" {
  description = "returns a set of string"
  value       = oci_golden_gate_deployment.this.nsg_ids
}

output "private_ip_address" {
  description = "returns a string"
  value       = oci_golden_gate_deployment.this.private_ip_address
}

output "public_ip_address" {
  description = "returns a string"
  value       = oci_golden_gate_deployment.this.public_ip_address
}

output "state" {
  description = "returns a string"
  value       = oci_golden_gate_deployment.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_golden_gate_deployment.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_golden_gate_deployment.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_golden_gate_deployment.this.time_updated
}

output "this" {
  value = oci_golden_gate_deployment.this
}
```

[top](#index)