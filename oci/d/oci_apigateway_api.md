# oci_apigateway_api

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
module "oci_apigateway_api" {
  source = "./modules/oci/d/oci_apigateway_api"

  # api_id - (required) is a type of string
  api_id = null
}
```

[top](#index)

### Variables

```terraform
variable "api_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_apigateway_api" "this" {
  api_id = var.api_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_apigateway_api.this.compartment_id
}

output "content" {
  description = "returns a string"
  value       = data.oci_apigateway_api.this.content
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_apigateway_api.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_apigateway_api.this.display_name
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_apigateway_api.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_apigateway_api.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_apigateway_api.this.lifecycle_details
}

output "specification_type" {
  description = "returns a string"
  value       = data.oci_apigateway_api.this.specification_type
}

output "state" {
  description = "returns a string"
  value       = data.oci_apigateway_api.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_apigateway_api.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_apigateway_api.this.time_updated
}

output "validation_results" {
  description = "returns a list of object"
  value       = data.oci_apigateway_api.this.validation_results
}

output "this" {
  value = oci_apigateway_api.this
}
```

[top](#index)