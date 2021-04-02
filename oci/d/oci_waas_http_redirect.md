# oci_waas_http_redirect

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
module "oci_waas_http_redirect" {
  source = "./modules/oci/d/oci_waas_http_redirect"

  # http_redirect_id - (required) is a type of string
  http_redirect_id = null
}
```

[top](#index)

### Variables

```terraform
variable "http_redirect_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_waas_http_redirect" "this" {
  http_redirect_id = var.http_redirect_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_waas_http_redirect.this.compartment_id
}

output "defined_tags" {
  description = "returns a map of string"
  value       = data.oci_waas_http_redirect.this.defined_tags
}

output "display_name" {
  description = "returns a string"
  value       = data.oci_waas_http_redirect.this.display_name
}

output "domain" {
  description = "returns a string"
  value       = data.oci_waas_http_redirect.this.domain
}

output "freeform_tags" {
  description = "returns a map of string"
  value       = data.oci_waas_http_redirect.this.freeform_tags
}

output "id" {
  description = "returns a string"
  value       = data.oci_waas_http_redirect.this.id
}

output "response_code" {
  description = "returns a number"
  value       = data.oci_waas_http_redirect.this.response_code
}

output "state" {
  description = "returns a string"
  value       = data.oci_waas_http_redirect.this.state
}

output "target" {
  description = "returns a list of object"
  value       = data.oci_waas_http_redirect.this.target
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_waas_http_redirect.this.time_created
}

output "this" {
  value = oci_waas_http_redirect.this
}
```

[top](#index)