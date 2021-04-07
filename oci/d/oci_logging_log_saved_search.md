# oci_logging_log_saved_search

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
module "oci_logging_log_saved_search" {
  source = "./modules/oci/d/oci_logging_log_saved_search"

  # log_saved_search_id - (required) is a type of string
  log_saved_search_id = null
}
```

[top](#index)

### Variables

```terraform
variable "log_saved_search_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_logging_log_saved_search" "this" {
  # log_saved_search_id - (required) is a type of string
  log_saved_search_id = var.log_saved_search_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_logging_log_saved_search.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_logging_log_saved_search.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_logging_log_saved_search.this.description
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_logging_log_saved_search.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_logging_log_saved_search.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_logging_log_saved_search.this.name
}

output "query" {
  description = "returns a string"
  value       = data.oci_logging_log_saved_search.this.query
}

output "state" {
  description = "returns a string"
  value       = data.oci_logging_log_saved_search.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_logging_log_saved_search.this.time_created
}

output "time_last_modified" {
  description = "returns a string"
  value       = data.oci_logging_log_saved_search.this.time_last_modified
}

output "this" {
  value = oci_logging_log_saved_search.this
}
```

[top](#index)