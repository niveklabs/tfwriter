# oci_objectstorage_namespace_metadata

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/oci/r/oci_objectstorage_namespace_metadata"

  # default_s3compartment_id - (optional) is a type of string
  default_s3compartment_id = null
  # default_swift_compartment_id - (optional) is a type of string
  default_swift_compartment_id = null
  # namespace - (required) is a type of string
  namespace = null

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "default_s3compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "default_swift_compartment_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_objectstorage_namespace_metadata" "this" {
  default_s3compartment_id     = var.default_s3compartment_id
  default_swift_compartment_id = var.default_swift_compartment_id
  namespace                    = var.namespace

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "default_s3compartment_id" {
  description = "returns a string"
  value       = oci_objectstorage_namespace_metadata.this.default_s3compartment_id
}

output "default_swift_compartment_id" {
  description = "returns a string"
  value       = oci_objectstorage_namespace_metadata.this.default_swift_compartment_id
}

output "id" {
  description = "returns a string"
  value       = oci_objectstorage_namespace_metadata.this.id
}

output "this" {
  value = oci_objectstorage_namespace_metadata.this
}
```

[top](#index)