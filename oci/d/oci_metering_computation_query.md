# oci_metering_computation_query

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
module "oci_metering_computation_query" {
  source = "./modules/oci/d/oci_metering_computation_query"

  # query_id - (required) is a type of string
  query_id = null
}
```

[top](#index)

### Variables

```terraform
variable "query_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_metering_computation_query" "this" {
  query_id = var.query_id
}
```

[top](#index)

### Outputs

```terraform
output "compartment_id" {
  description = "returns a string"
  value       = data.oci_metering_computation_query.this.compartment_id
}

output "id" {
  description = "returns a string"
  value       = data.oci_metering_computation_query.this.id
}

output "query_definition" {
  description = "returns a list of object"
  value       = data.oci_metering_computation_query.this.query_definition
}

output "this" {
  value = oci_metering_computation_query.this
}
```

[top](#index)