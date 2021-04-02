# oci_core_compute_global_image_capability_schemas_versions

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
module "oci_core_compute_global_image_capability_schemas_versions" {
  source = "./modules/oci/d/oci_core_compute_global_image_capability_schemas_versions"

  # compute_global_image_capability_schema_id - (required) is a type of string
  compute_global_image_capability_schema_id = null
  # display_name - (optional) is a type of string
  display_name = null

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
variable "compute_global_image_capability_schema_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
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
data "oci_core_compute_global_image_capability_schemas_versions" "this" {
  compute_global_image_capability_schema_id = var.compute_global_image_capability_schema_id
  display_name                              = var.display_name

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
output "compute_global_image_capability_schema_versions" {
  description = "returns a list of object"
  value       = data.oci_core_compute_global_image_capability_schemas_versions.this.compute_global_image_capability_schema_versions
}

output "id" {
  description = "returns a string"
  value       = data.oci_core_compute_global_image_capability_schemas_versions.this.id
}

output "this" {
  value = oci_core_compute_global_image_capability_schemas_versions.this
}
```

[top](#index)