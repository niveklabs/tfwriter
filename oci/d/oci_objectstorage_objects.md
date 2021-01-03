# oci_objectstorage_objects

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
module "oci_objectstorage_objects" {
  source = "./modules/oci/d/oci_objectstorage_objects"

  # bucket - (required) is a type of string
  bucket = null
  # delimiter - (optional) is a type of string
  delimiter = null
  # end - (optional) is a type of string
  end = null
  # namespace - (required) is a type of string
  namespace = null
  # prefix - (optional) is a type of string
  prefix = null
  # start - (optional) is a type of string
  start = null
  # start_after - (optional) is a type of string
  start_after = null

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

variable "delimiter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "end" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "prefix" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "start_after" {
  description = "(optional)"
  type        = string
  default     = null
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
data "oci_objectstorage_objects" "this" {
  bucket      = var.bucket
  delimiter   = var.delimiter
  end         = var.end
  namespace   = var.namespace
  prefix      = var.prefix
  start       = var.start
  start_after = var.start_after

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
  value       = data.oci_objectstorage_objects.this.id
}

output "objects" {
  description = "returns a list of object"
  value       = data.oci_objectstorage_objects.this.objects
}

output "this" {
  value = oci_objectstorage_objects.this
}
```

[top](#index)