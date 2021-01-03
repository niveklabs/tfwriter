# oci_apigateway_gateway

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
module "oci_apigateway_gateway" {
  source = "./modules/oci/d/oci_apigateway_gateway"

  # gateway_id - (required) is a type of string
  gateway_id = null
}
```

[top](#index)

### Variables

```terraform
variable "gateway_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_apigateway_gateway" "this" {
  gateway_id = var.gateway_id
}
```

[top](#index)

### Outputs

```terraform
output "certificate_id" {
  description = "returns a string"
  value       = data.oci_apigateway_gateway.this.certificate_id
}

output "compartment_id" {
  description = "returns a string"
  value       = data.oci_apigateway_gateway.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_apigateway_gateway.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_apigateway_gateway.this.display_name
}

output "endpoint_type" {
  description = "returns a string"
  value       = data.oci_apigateway_gateway.this.endpoint_type
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_apigateway_gateway.this.freeform_tags
}

output "hostname" {
  description = "returns a string"
  value       = data.oci_apigateway_gateway.this.hostname
}

output "id" {
  description = "returns a string"
  value       = data.oci_apigateway_gateway.this.id
}

output "ip_addresses" {
  description = "returns a list of object"
  value       = data.oci_apigateway_gateway.this.ip_addresses
}

output "lifecycle_details" {
  description = "returns a string"
  value       = data.oci_apigateway_gateway.this.lifecycle_details
}

output "state" {
  description = "returns a string"
  value       = data.oci_apigateway_gateway.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_apigateway_gateway.this.subnet_id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_apigateway_gateway.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_apigateway_gateway.this.time_updated
}

output "this" {
  value = oci_apigateway_gateway.this
}
```

[top](#index)