# oci_objectstorage_replication_policies

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
module "oci_objectstorage_replication_policies" {
  source = "./modules/oci/d/oci_objectstorage_replication_policies"

  # bucket - (required) is a type of string
  bucket = null
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
variable "bucket" {
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
data "oci_objectstorage_replication_policies" "this" {
  bucket    = var.bucket
  namespace = var.namespace

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
output "id" {
  description = "returns a string"
  value       = data.oci_objectstorage_replication_policies.this.id
}

output "replication_policies" {
  description = "returns a list of object"
  value       = data.oci_objectstorage_replication_policies.this.replication_policies
}

output "this" {
  value = oci_objectstorage_replication_policies.this
}
```

[top](#index)