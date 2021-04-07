# oci_objectstorage_namespace

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
module "oci_objectstorage_namespace" {
  source = "./modules/oci/d/oci_objectstorage_namespace"

  # compartment_id - (optional) is a type of string
  compartment_id = null
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "oci_objectstorage_namespace" "this" {
  # compartment_id - (optional) is a type of string
  compartment_id = var.compartment_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_objectstorage_namespace.this.id
}

output "namespace" {
  description = "returns a string"
  value       = data.oci_objectstorage_namespace.this.namespace
}

output "this" {
  value = oci_objectstorage_namespace.this
}
```

[top](#index)