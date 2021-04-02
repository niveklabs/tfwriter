# oci_identity_tag

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_identity_tag" {
  source = "./modules/oci/d/oci_identity_tag"

  # tag_name - (required) is a type of string
  tag_name = null
  # tag_namespace_id - (required) is a type of string
  tag_namespace_id = null
}
```

[top](#index)

### Variables

```terraform
variable "tag_name" {
  description = "(required)"
  type        = string
}

variable "tag_namespace_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_identity_tag" "this" {
  tag_name         = var.tag_name
  tag_namespace_id = var.tag_namespace_id
}
```

[top](#index)

### Outputs

```terraform
output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_tag.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_identity_tag.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_identity_tag.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_identity_tag.this.id
}

output "is_cost_tracking" {
  description = "returns a bool"
  value       = data.oci_identity_tag.this.is_cost_tracking
}

output "is_retired" {
  description = "returns a bool"
  value       = data.oci_identity_tag.this.is_retired
}

output "name" {
  description = "returns a string"
  value       = data.oci_identity_tag.this.name
}

output "state" {
  description = "returns a string"
  value       = data.oci_identity_tag.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_identity_tag.this.time_created
}

output "validator" {
  description = "returns a list of object"
  value       = data.oci_identity_tag.this.validator
}

output "this" {
  value = oci_identity_tag.this
}
```

[top](#index)