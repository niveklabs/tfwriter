# oci_datascience_model_deployment

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_datascience_model_deployment" {
  source = "./modules/oci/d/oci_datascience_model_deployment"

  # model_deployment_id - (required) is a type of string
  model_deployment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "model_deployment_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_datascience_model_deployment" "this" {
  model_deployment_id = var.model_deployment_id
}
```

[top](#index)

### Outputs

```terraform
output "category_log_details" {
  description = "returns a list of object"
  value       = data.oci_datascience_model_deployment.this.category_log_details
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_datascience_model_deployment.this.compartment_id
}

output "created_by" {
  description = "returns a string"
  value       = data.oci_datascience_model_deployment.this.created_by
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_datascience_model_deployment.this.defined_tags
}

output "description" {
  description = "returns a string"
  value       = data.oci_datascience_model_deployment.this.description
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_datascience_model_deployment.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_datascience_model_deployment.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_datascience_model_deployment.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_datascience_model_deployment.this.lifecycle_details
}

output "model_deployment_configuration_details" {
  description = "returns a list of object"
  value       = data.oci_datascience_model_deployment.this.model_deployment_configuration_details
}

output "model_deployment_url" {
  description = "returns a string"
  value       = data.oci_datascience_model_deployment.this.model_deployment_url
}

output "project_id" {
  description = "returns a string"
  value       = data.oci_datascience_model_deployment.this.project_id
}

output "state" {
  description = "returns a string"
  value       = data.oci_datascience_model_deployment.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_datascience_model_deployment.this.time_created
}

output "this" {
  value = oci_datascience_model_deployment.this
}
```

[top](#index)