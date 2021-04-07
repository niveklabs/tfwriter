# oci_dns_resolver_endpoint

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
module "oci_dns_resolver_endpoint" {
  source = "./modules/oci/d/oci_dns_resolver_endpoint"

  # resolver_endpoint_name - (required) is a type of string
  resolver_endpoint_name = null
  # resolver_id - (required) is a type of string
  resolver_id = null
  # scope - (required) is a type of string
  scope = null
}
```

[top](#index)

### Variables

```terraform
variable "resolver_endpoint_name" {
  description = "(required)"
  type        = string
}

variable "resolver_id" {
  description = "(required)"
  type        = string
}

variable "scope" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_dns_resolver_endpoint" "this" {
  resolver_endpoint_name = var.resolver_endpoint_name
  resolver_id            = var.resolver_id
  scope                  = var.scope
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoint.this.compartment_id
}

output "endpoint_type" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoint.this.endpoint_type
}

output "forwarding_address" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoint.this.forwarding_address
}

output "id" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoint.this.id
}

output "is_forwarding" {
  description = "returns a bool"
  value       = data.oci_dns_resolver_endpoint.this.is_forwarding
}

output "is_listening" {
  description = "returns a bool"
  value       = data.oci_dns_resolver_endpoint.this.is_listening
}

output "listening_address" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoint.this.listening_address
}

output "name" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoint.this.name
}

output "nsg_ids" {
  description = "returns a list of string"
  value       = data.oci_dns_resolver_endpoint.this.nsg_ids
}

output "self" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoint.this.self
}

output "state" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoint.this.state
}

output "subnet_id" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoint.this.subnet_id
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoint.this.time_created
}

output "time_updated" {
  description = "returns a string"
  value       = data.oci_dns_resolver_endpoint.this.time_updated
}

output "this" {
  value = oci_dns_resolver_endpoint.this
}
```

[top](#index)