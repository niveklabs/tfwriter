# oci_identity_tag_default

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_identity_tag_default" {
  source = "./modules/oci/d/oci_identity_tag_default"

  # tag_default_id - (required) is a type of string
  tag_default_id = null
}
```

[top](#index)

### Variables

```terraform
variable "tag_default_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_identity_tag_default" "this" {
  # tag_default_id - (required) is a type of string
  tag_default_id = var.tag_default_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_identity_tag_default.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = data.oci_identity_tag_default.this.id
}

output "is_required" {
  description = "returns a bool"
  value       = data.oci_identity_tag_default.this.is_required
}

output "state" {
  description = "returns a string"
  value       = data.oci_identity_tag_default.this.state
}

output "tag_definition_id" {
  description = "returns a string"
  value       = data.oci_identity_tag_default.this.tag_definition_id
}

output "tag_definition_name" {
  description = "returns a string"
  value       = data.oci_identity_tag_default.this.tag_definition_name
}

output "tag_namespace_id" {
  description = "returns a string"
  value       = data.oci_identity_tag_default.this.tag_namespace_id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_identity_tag_default.this.time_created
}

output "value" {
  description = "returns a string"
  value       = data.oci_identity_tag_default.this.value
}

output "this" {
  value = oci_identity_tag_default.this
}
```

[top](#index)