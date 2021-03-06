# oci_objectstorage_object_lifecycle_policy

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
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_objectstorage_object_lifecycle_policy" {
  source = "./modules/oci/r/oci_objectstorage_object_lifecycle_policy"

  # bucket - (required) is a type of string
  bucket = null
  # namespace - (required) is a type of string
  namespace = null

  rules = [{
    action     = null
    is_enabled = null
    name       = null
    object_name_filter = [{
      exclusion_patterns = []
      inclusion_patterns = []
      inclusion_prefixes = []
    }]
    target      = null
    time_amount = null
    time_unit   = null
  }]

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
variable "bucket" {
  description = "(required)"
  type        = string
}

variable "namespace" {
  description = "(required)"
  type        = string
}

variable "rules" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      action     = string
      is_enabled = bool
      name       = string
      object_name_filter = list(object(
        {
          exclusion_patterns = set(string)
          inclusion_patterns = set(string)
          inclusion_prefixes = set(string)
        }
      ))
      target      = string
      time_amount = string
      time_unit   = string
    }
  ))
  default = []
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
resource "oci_objectstorage_object_lifecycle_policy" "this" {
  # bucket - (required) is a type of string
  bucket = var.bucket
  # namespace - (required) is a type of string
  namespace = var.namespace

  dynamic "rules" {
    for_each = var.rules
    content {
      # action - (required) is a type of string
      action = rules.value["action"]
      # is_enabled - (required) is a type of bool
      is_enabled = rules.value["is_enabled"]
      # name - (required) is a type of string
      name = rules.value["name"]
      # target - (optional) is a type of string
      target = rules.value["target"]
      # time_amount - (required) is a type of string
      time_amount = rules.value["time_amount"]
      # time_unit - (required) is a type of string
      time_unit = rules.value["time_unit"]

      dynamic "object_name_filter" {
        for_each = rules.value.object_name_filter
        content {
          # exclusion_patterns - (optional) is a type of set of string
          exclusion_patterns = object_name_filter.value["exclusion_patterns"]
          # inclusion_patterns - (optional) is a type of set of string
          inclusion_patterns = object_name_filter.value["inclusion_patterns"]
          # inclusion_prefixes - (optional) is a type of set of string
          inclusion_prefixes = object_name_filter.value["inclusion_prefixes"]
        }
      }

    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      # create - (optional) is a type of string
      create = timeouts.value["create"]
      # delete - (optional) is a type of string
      delete = timeouts.value["delete"]
      # update - (optional) is a type of string
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = oci_objectstorage_object_lifecycle_policy.this.id
}

output "time_created" {
  description = "returns a string"
  value       = oci_objectstorage_object_lifecycle_policy.this.time_created
}

output "this" {
  value = oci_objectstorage_object_lifecycle_policy.this
}
```

[top](#index)