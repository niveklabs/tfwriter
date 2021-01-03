# oci_optimizer_profile

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
module "oci_optimizer_profile" {
  source = "./modules/oci/d/oci_optimizer_profile"

  # profile_id - (required) is a type of string
  profile_id = null
}
```

[top](#index)

### Variables

```terraform
variable "profile_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_optimizer_profile" "this" {
  profile_id = var.profile_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_optimizer_profile.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_optimizer_profile.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_optimizer_profile.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_optimizer_profile.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_optimizer_profile.this.id
}

output "levels_configuration" {
  description = "returns a list of object"
  value       = data.oci_optimizer_profile.this.levels_configuration
}

output "name" {
  description = "returns a string"
  value       = data.oci_optimizer_profile.this.name
}

output "state" {
  description = "returns a string"
  value       = data.oci_optimizer_profile.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_optimizer_profile.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_optimizer_profile.this.time_updated
}

output "this" {
  value = oci_optimizer_profile.this
}
```

[top](#index)