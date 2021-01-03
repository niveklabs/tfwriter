# oci_cloud_guard_responder_recipe

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
module "oci_cloud_guard_responder_recipe" {
  source = "./modules/oci/d/oci_cloud_guard_responder_recipe"

  # responder_recipe_id - (required) is a type of string
  responder_recipe_id = null
}
```

[top](#index)

### Variables

```terraform
variable "responder_recipe_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_cloud_guard_responder_recipe" "this" {
  responder_recipe_id = var.responder_recipe_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_responder_recipe.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_responder_recipe.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_cloud_guard_responder_recipe.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_cloud_guard_responder_recipe.this.display_name
}

output "effective_responder_rules" {
  description = "returns a list of object"
  value       = data.oci_cloud_guard_responder_recipe.this.effective_responder_rules
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_responder_recipe.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_responder_recipe.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_cloud_guard_responder_recipe.this.lifecycle_details
}

output "owner" {
  description = "returns a string"
  value       = data.oci_cloud_guard_responder_recipe.this.owner
}

output "responder_rules" {
  description = "returns a list of object"
  value       = data.oci_cloud_guard_responder_recipe.this.responder_rules
}

output "source_responder_recipe_id" {
  description = "returns a string"
  value       = data.oci_cloud_guard_responder_recipe.this.source_responder_recipe_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_cloud_guard_responder_recipe.this.state
}

output "system_tags" {
  description = "returns a map of string"
  value       = data.oci_cloud_guard_responder_recipe.this.system_tags
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_cloud_guard_responder_recipe.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_cloud_guard_responder_recipe.this.time_updated
}

output "this" {
  value = oci_cloud_guard_responder_recipe.this
}
```

[top](#index)