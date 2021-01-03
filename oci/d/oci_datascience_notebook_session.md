# oci_datascience_notebook_session

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
module "oci_datascience_notebook_session" {
  source = "./modules/oci/d/oci_datascience_notebook_session"

  # notebook_session_id - (required) is a type of string
  notebook_session_id = null
}
```

[top](#index)

### Variables

```terraform
variable "notebook_session_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_datascience_notebook_session" "this" {
  notebook_session_id = var.notebook_session_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_datascience_notebook_session.this.compartment_id
}

output "created_by" {
  description = "returns a string"
  value       = data.oci_datascience_notebook_session.this.created_by
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_datascience_notebook_session.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_datascience_notebook_session.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_datascience_notebook_session.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_datascience_notebook_session.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_datascience_notebook_session.this.lifecycle_details
}

output "notebook_session_configuration_details" {
  description = "returns a list of object"
  value       = data.oci_datascience_notebook_session.this.notebook_session_configuration_details
}

output "notebook_session_url" {
  description = "returns a string"
  value       = data.oci_datascience_notebook_session.this.notebook_session_url
}

output "project_id" {
  description = "returns a string"
  value       = data.oci_datascience_notebook_session.this.project_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_datascience_notebook_session.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_datascience_notebook_session.this.time_created
}

output "this" {
  value = oci_datascience_notebook_session.this
}
```

[top](#index)