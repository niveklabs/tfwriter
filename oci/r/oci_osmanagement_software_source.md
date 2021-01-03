# oci_osmanagement_software_source

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
    oci = ">= 4.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_osmanagement_software_source" {
  source = "./modules/oci/r/oci_osmanagement_software_source"

  # arch_type - (required) is a type of string
  arch_type = null
  # checksum_type - (optional) is a type of string
  checksum_type = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # defined_tags - (optional) is a type of map of string
  defined_tags = {}
  # description - (optional) is a type of string
  description = null
  # display_name - (required) is a type of string
  display_name = null
  # freeform_tags - (optional) is a type of map of string
  freeform_tags = {}
  # maintainer_email - (optional) is a type of string
  maintainer_email = null
  # maintainer_name - (optional) is a type of string
  maintainer_name = null
  # maintainer_phone - (optional) is a type of string
  maintainer_phone = null
  # parent_id - (optional) is a type of string
  parent_id = null

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
variable "arch_type" {
  description = "(required)"
  type        = string
}

variable "checksum_type" {
  description = "(optional)"
  type        = string
  default     = null
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

variable "display_name" {
  description = "(required)"
  type        = string
}

variable "freeform_tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "maintainer_email" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maintainer_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "maintainer_phone" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent_id" {
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
resource "oci_osmanagement_software_source" "this" {
  arch_type        = var.arch_type
  checksum_type    = var.checksum_type
  compartment_id   = var.compartment_id
  defined_tags     = var.defined_tags
  description      = var.description
  display_name     = var.display_name
  freeform_tags    = var.freeform_tags
  maintainer_email = var.maintainer_email
  maintainer_name  = var.maintainer_name
  maintainer_phone = var.maintainer_phone
  parent_id        = var.parent_id

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
output "associated_managed_instances" {
  description = "returns a list of object"
  value       = oci_osmanagement_software_source.this.associated_managed_instances
}

output "checksum_type" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.checksum_type
}

output "defined_tags" {
  description = "returns a map of string"
  value       = oci_osmanagement_software_source.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = oci_osmanagement_software_source.this.freeform_tags
}

output "gpg_key_fingerprint" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.gpg_key_fingerprint
}

output "gpg_key_id" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.gpg_key_id
}

output "gpg_key_url" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.gpg_key_url
}

output "id" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.id
}

output "maintainer_email" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.maintainer_email
}

output "maintainer_name" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.maintainer_name
}

output "maintainer_phone" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.maintainer_phone
}

output "packages" {
  description = "returns a number"
  value       = oci_osmanagement_software_source.this.packages
}

output "parent_id" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.parent_id
}

output "parent_name" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.parent_name
}

output "repo_type" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.repo_type
}

output "state" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.state
}

output "status" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.status
}

output "url" {
  description = "returns a string"
  value       = oci_osmanagement_software_source.this.url
}

output "this" {
  value = oci_osmanagement_software_source.this
}
```

[top](#index)