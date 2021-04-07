# oci_logging_log_saved_searches

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
module "oci_logging_log_saved_searches" {
  source = "./modules/oci/d/oci_logging_log_saved_searches"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # log_saved_search_id - (optional) is a type of string
  log_saved_search_id = null
  # name - (optional) is a type of string
  name = null

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

variable "log_saved_search_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
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
data "oci_logging_log_saved_searches" "this" {
  compartment_id      = var.compartment_id
  log_saved_search_id = var.log_saved_search_id
  name                = var.name

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
  value       = data.oci_logging_log_saved_searches.this.id
}

output "log_saved_search_summary_collection" {
  description = "returns a list of object"
  value       = data.oci_logging_log_saved_searches.this.log_saved_search_summary_collection
}

output "this" {
  value = oci_logging_log_saved_searches.this
}
```

[top](#index)