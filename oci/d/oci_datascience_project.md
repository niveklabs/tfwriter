# oci_datascience_project

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
module "oci_datascience_project" {
  source = "./modules/oci/d/oci_datascience_project"

  # project_id - (required) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_datascience_project" "this" {
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_datascience_project.this.compartment_id
}

output "created_by" {
  description = "returns a string"
  value       = data.oci_datascience_project.this.created_by
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_datascience_project.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_datascience_project.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_datascience_project.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_datascience_project.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_datascience_project.this.id
}

output "state" {
  description = "returns a string"
  value       = data.oci_datascience_project.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_datascience_project.this.time_created
}

output "this" {
  value = oci_datascience_project.this
}
```

[top](#index)