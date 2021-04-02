# oci_apigateway_deployment

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
module "oci_apigateway_deployment" {
  source = "./modules/oci/d/oci_apigateway_deployment"

  # deployment_id - (required) is a type of string
  deployment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "deployment_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_apigateway_deployment" "this" {
  deployment_id = var.deployment_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_apigateway_deployment.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_apigateway_deployment.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_apigateway_deployment.this.display_name
}

output "endpoint" {
  description = "returns a string"
  value       = data.oci_apigateway_deployment.this.endpoint
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_apigateway_deployment.this.freeform_tags
}

output "gateway_id" {
  description = "returns a string"
  value       = data.oci_apigateway_deployment.this.gateway_id
}

output "id" {
  description = "returns a string"
  value       = data.oci_apigateway_deployment.this.id
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_apigateway_deployment.this.lifecycle_details
}

output "path_prefix" {
  description = "returns a string"
  value       = data.oci_apigateway_deployment.this.path_prefix
}

output "specification" {
  description = "returns a list of object"
  value       = data.oci_apigateway_deployment.this.specification
}

output "state" {
  description = "returns a string"
  value       = data.oci_apigateway_deployment.this.state
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_apigateway_deployment.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_apigateway_deployment.this.time_updated
}

output "this" {
  value = oci_apigateway_deployment.this
}
```

[top](#index)