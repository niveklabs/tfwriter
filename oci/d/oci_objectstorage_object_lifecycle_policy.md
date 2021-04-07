# oci_objectstorage_object_lifecycle_policy

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
module "oci_objectstorage_object_lifecycle_policy" {
  source = "./modules/oci/d/oci_objectstorage_object_lifecycle_policy"

  # bucket - (required) is a type of string
  bucket = null
  # namespace - (required) is a type of string
  namespace = null
}
```

[top](#index)

### Variables

```terraform
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_objectstorage_object_lifecycle_policy" "this" {
  bucket    = var.bucket
  namespace = var.namespace
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_objectstorage_object_lifecycle_policy.this.id
}

output "rules" {
  description = "returns a list of object"
  value       = data.oci_objectstorage_object_lifecycle_policy.this.rules
}

output "time_created" {
  description = "returns a string"
  value       = data.oci_objectstorage_object_lifecycle_policy.this.time_created
}

output "this" {
  value = oci_objectstorage_object_lifecycle_policy.this
}
```

[top](#index)