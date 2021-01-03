# oci_osmanagement_software_source

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/oci/d/oci_osmanagement_software_source"

  # software_source_id - (required) is a type of string
  software_source_id = null
}
```

[top](#index)

### Variables

```terraform
variable "software_source_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_osmanagement_software_source" "this" {
  software_source_id = var.software_source_id
}
```

[top](#index)

### Outputs

```terraform
output "arch_type" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.arch_type
}

output "associated_managed_instances" {
  description = "returns a list of object"
  value       = data.oci_osmanagement_software_source.this.associated_managed_instances
}

output "checksum_type" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.checksum_type
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_osmanagement_software_source.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_osmanagement_software_source.this.freeform_tags
}

output "gpg_key_fingerprint" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.gpg_key_fingerprint
}

output "gpg_key_id" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.gpg_key_id
}

output "gpg_key_url" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.gpg_key_url
}

output "id" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.id
}

output "maintainer_email" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.maintainer_email
}

output "maintainer_name" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.maintainer_name
}

output "maintainer_phone" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.maintainer_phone
}

output "packages" {
  description = "returns a number"
  value       = data.oci_osmanagement_software_source.this.packages
}

output "parent_id" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.parent_id
}

output "parent_name" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.parent_name
}

output "repo_type" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.repo_type
}

output "state" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.state
}

output "status" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.status
}

output "url" {
  description = "returns a string"
  value       = data.oci_osmanagement_software_source.this.url
}

output "this" {
  value = oci_osmanagement_software_source.this
}
```

[top](#index)