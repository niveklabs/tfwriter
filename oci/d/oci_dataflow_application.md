# oci_dataflow_application

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
module "oci_dataflow_application" {
  source = "./modules/oci/d/oci_dataflow_application"

  # application_id - (required) is a type of string
  application_id = null
}
```

[top](#index)

### Variables

```terraform
variable "application_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_dataflow_application" "this" {
  application_id = var.application_id
}
```

[top](#index)

### Outputs

```terraform
output "archive_uri" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.archive_uri
}

output "arguments" {
  description = "returns a list of string"
  value       = data.oci_dataflow_application.this.arguments
}

output "class_name" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.class_name
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.compartment_id
}

output "configuration" {
  description = "returns a map of string"
  value       = data.oci_dataflow_application.this.configuration
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_dataflow_application.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.display_name
}

output "driver_shape" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.driver_shape
}

output "executor_shape" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.executor_shape
}

output "file_uri" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.file_uri
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_dataflow_application.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.id
}

output "language" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.language
}

output "logs_bucket_uri" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.logs_bucket_uri
}

output "num_executors" {
  description = "returns a number"
  value       = data.oci_dataflow_application.this.num_executors
}

output "owner_principal_id" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.owner_principal_id
}

output "owner_user_name" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.owner_user_name
}

output "parameters" {
  description = "returns a list of object"
  value       = data.oci_dataflow_application.this.parameters
}

output "private_endpoint_id" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.private_endpoint_id
}

output "spark_version" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.spark_version
}

output "state" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.time_updated
}

output "warehouse_bucket_uri" {
  description = "returns a string"
  value       = data.oci_dataflow_application.this.warehouse_bucket_uri
}

output "this" {
  value = oci_dataflow_application.this
}
```

[top](#index)