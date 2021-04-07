# oci_artifacts_container_configuration

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
module "oci_artifacts_container_configuration" {
  source = "./modules/oci/d/oci_artifacts_container_configuration"

  # compartment_id - (required) is a type of string
  compartment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_artifacts_container_configuration" "this" {
  compartment_id = var.compartment_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_artifacts_container_configuration.this.id
}

output "is_repository_created_on_first_push" {
  description = "returns a bool"
  value       = data.oci_artifacts_container_configuration.this.is_repository_created_on_first_push
}

output "namespace" {
  description = "returns a string"
  value       = data.oci_artifacts_container_configuration.this.namespace
}

output "this" {
  value = oci_artifacts_container_configuration.this
}
```

[top](#index)