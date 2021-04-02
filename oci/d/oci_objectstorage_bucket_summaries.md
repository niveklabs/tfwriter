# oci_objectstorage_bucket_summaries

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
module "oci_objectstorage_bucket_summaries" {
  source = "./modules/oci/d/oci_objectstorage_bucket_summaries"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # namespace - (required) is a type of string
  namespace = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_objectstorage_bucket_summaries" "this" {
  compartment_id = var.compartment_id
  namespace      = var.namespace

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "bucket_summaries" {
  description = "returns a list of object"
  value       = data.oci_objectstorage_bucket_summaries.this.bucket_summaries
}

output "id" {
  description = "returns a string"
  value       = data.oci_objectstorage_bucket_summaries.this.id
}

output "this" {
  value = oci_objectstorage_bucket_summaries.this
}
```

[top](#index)