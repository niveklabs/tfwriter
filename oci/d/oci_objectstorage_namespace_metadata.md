# oci_objectstorage_namespace_metadata

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
module "oci_objectstorage_namespace_metadata" {
  source = "./modules/oci/d/oci_objectstorage_namespace_metadata"

  # namespace - (required) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "namespace" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_objectstorage_namespace_metadata" "this" {
  namespace = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "default_s3compartment_id" {
  description = "returns a string"
  value       = data.oci_objectstorage_namespace_metadata.this.default_s3compartment_id
}

output "default_swift_compartment_id" {
  description = "returns a string"
  value       = data.oci_objectstorage_namespace_metadata.this.default_swift_compartment_id
}

output "id" {
  description = "returns a string"
  value       = data.oci_objectstorage_namespace_metadata.this.id
}

output "this" {
  value = oci_objectstorage_namespace_metadata.this
}
```

[top](#index)