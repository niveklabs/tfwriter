# oci_data_safe_on_prem_connectors

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
module "oci_data_safe_on_prem_connectors" {
  source = "./modules/oci/d/oci_data_safe_on_prem_connectors"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # on_prem_connector_id - (optional) is a type of string
  on_prem_connector_id = null
  # on_prem_connector_lifecycle_state - (optional) is a type of string
  on_prem_connector_lifecycle_state = null

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

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "on_prem_connector_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "on_prem_connector_lifecycle_state" {
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
data "oci_data_safe_on_prem_connectors" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # display_name - (optional) is a type of string
  display_name = var.display_name
  # on_prem_connector_id - (optional) is a type of string
  on_prem_connector_id = var.on_prem_connector_id
  # on_prem_connector_lifecycle_state - (optional) is a type of string
  on_prem_connector_lifecycle_state = var.on_prem_connector_lifecycle_state

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # regex - (optional) is a type of bool
      regex = filter.value["regex"]
      # values - (required) is a type of list of string
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
  value       = data.oci_data_safe_on_prem_connectors.this.id
}

output "on_prem_connectors" {
  description = "returns a list of object"
  value       = data.oci_data_safe_on_prem_connectors.this.on_prem_connectors
}

output "this" {
  value = oci_data_safe_on_prem_connectors.this
}
```

[top](#index)