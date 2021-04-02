# oci_apigateway_api_deployment_specification

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
module "oci_apigateway_api_deployment_specification" {
  source = "./modules/oci/d/oci_apigateway_api_deployment_specification"

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
data "oci_apigateway_api_deployment_specification" "this" {
  api_id = var.api_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_apigateway_api_deployment_specification.this.id
}

output "logging_policies" {
  description = "returns a list of object"
  value       = data.oci_apigateway_api_deployment_specification.this.logging_policies
}

output "request_policies" {
  description = "returns a list of object"
  value       = data.oci_apigateway_api_deployment_specification.this.request_policies
}

output "routes" {
  description = "returns a list of object"
  value       = data.oci_apigateway_api_deployment_specification.this.routes
}

output "this" {
  value = oci_apigateway_api_deployment_specification.this
}
```

[top](#index)