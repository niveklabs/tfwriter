# oci_golden_gate_deployment_backup

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
module "oci_golden_gate_deployment_backup" {
  source = "./modules/oci/r/oci_golden_gate_deployment_backup"

  # bucket - (required) is a type of string
  bucket = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # deployment_id - (required) is a type of string
  deployment_id = null
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # namespace - (required) is a type of string
  namespace = null
  # object - (required) is a type of string
  object = null

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
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "defined_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "deployment_id" {
  description = "(required)"
  type        = string
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

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "object" {
  description = "(required)"
  type        = string
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
resource "oci_golden_gate_deployment_backup" "this" {
  bucket         = var.bucket
  compartment_id = var.compartment_id
  defined_tags   = var.defined_tags
  deployment_id  = var.deployment_id
  display_name   = var.display_name
  freeform_tags  = var.freeform_tags
  namespace      = var.namespace
  object         = var.object

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
output "backup_type" {
  description = "returns a string"
  value       = oci_golden_gate_deployment_backup.this.backup_type
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_golden_gate_deployment_backup.this.defined_tags
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_golden_gate_deployment_backup.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = oci_golden_gate_deployment_backup.this.id
}

output "is_automatic" {
  description = "returns a bool"
  value       = oci_golden_gate_deployment_backup.this.is_automatic
}

output "lifecycle_details" {
  description = "returns a string"
  value       = oci_golden_gate_deployment_backup.this.lifecycle_details
}

output "ogg_version" {
  description = "returns a string"
  value       = oci_golden_gate_deployment_backup.this.ogg_version
}

output "state" {
  description = "returns a string"
  value       = oci_golden_gate_deployment_backup.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = oci_golden_gate_deployment_backup.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = oci_golden_gate_deployment_backup.this.time_created
}

output "time_of_backup" {
  description = "returns a string"
  value       = oci_golden_gate_deployment_backup.this.time_of_backup
}

output "time_updated" {
  description = "returns a string"
  value       = oci_golden_gate_deployment_backup.this.time_updated
}

output "this" {
  value = oci_golden_gate_deployment_backup.this
}
```

[top](#index)