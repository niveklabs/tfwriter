# oci_oce_oce_instance

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
module "oci_oce_oce_instance" {
  source = "./modules/oci/r/oci_oce_oce_instance"

  # admin_email - (required) is a type of string
  admin_email = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # idcs_access_token - (required) is a type of string
  idcs_access_token = null
  # instance_access_type - (optional) is a type of string
  instance_access_type = null
  # instance_license_type - (optional) is a type of string
  instance_license_type = null
  # instance_usage_type - (optional) is a type of string
  instance_usage_type = null
  # name - (required) is a type of string
  name = null
  # object_storage_namespace - (required) is a type of string
  object_storage_namespace = null
  # tenancy_id - (required) is a type of string
  tenancy_id = null
  # tenancy_name - (required) is a type of string
  tenancy_name = null
  # upgrade_schedule - (optional) is a type of string
  upgrade_schedule = null
  # waf_primary_domain - (optional) is a type of string
  waf_primary_domain = null

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
variable "admin_email" {
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

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "idcs_access_token" {
  description = "(required)"
  type        = string
}

variable "instance_access_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_license_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "instance_usage_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(required)"
  type        = string
}

variable "object_storage_namespace" {
  description = "(required)"
  type        = string
}

variable "tenancy_id" {
  description = "(required)"
  type        = string
}

variable "tenancy_name" {
  description = "(required)"
  type        = string
}

variable "upgrade_schedule" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "waf_primary_domain" {
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
resource "oci_oce_oce_instance" "this" {
  admin_email              = var.admin_email
  compartment_id           = var.compartment_id
  defined_tags             = var.defined_tags
  description              = var.description
  freeform_tags            = var.freeform_tags
  idcs_access_token        = var.idcs_access_token
  instance_access_type     = var.instance_access_type
  instance_license_type    = var.instance_license_type
  instance_usage_type      = var.instance_usage_type
  name                     = var.name
  object_storage_namespace = var.object_storage_namespace
  tenancy_id               = var.tenancy_id
  tenancy_name             = var.tenancy_name
  upgrade_schedule         = var.upgrade_schedule
  waf_primary_domain       = var.waf_primary_domain

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
  value       = oci_oce_oce_instance.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_oce_oce_instance.this.freeform_tags
}

output "guid" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.guid
}

output "id" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.id
}

output "idcs_tenancy" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.idcs_tenancy
}

output "instance_access_type" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.instance_access_type
}

output "instance_license_type" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.instance_license_type
}

output "instance_usage_type" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.instance_usage_type
}

output "service" {
  description = "returns a map of string"
  value       = oci_oce_oce_instance.this.service
}

output "state" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.state
}

output "state_message" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.state_message
}

output "time_created" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.time_updated
}

output "upgrade_schedule" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.upgrade_schedule
}

output "waf_primary_domain" {
  description = "returns a string"
  value       = oci_oce_oce_instance.this.waf_primary_domain
}

output "this" {
  value = oci_oce_oce_instance.this
}
```

[top](#index)