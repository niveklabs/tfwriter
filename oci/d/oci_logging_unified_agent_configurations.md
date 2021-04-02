# oci_logging_unified_agent_configurations

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
module "oci_logging_unified_agent_configurations" {
  source = "./modules/oci/d/oci_logging_unified_agent_configurations"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # group_id - (optional) is a type of string
  group_id = null
  # is_compartment_id_in_subtree - (optional) is a type of bool
  is_compartment_id_in_subtree = null
  # log_id - (optional) is a type of string
  log_id = null
  # state - (optional) is a type of string
  state = null

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

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_compartment_id_in_subtree" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "log_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
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
data "oci_logging_unified_agent_configurations" "this" {
  compartment_id               = var.compartment_id
  display_name                 = var.display_name
  group_id                     = var.group_id
  is_compartment_id_in_subtree = var.is_compartment_id_in_subtree
  log_id                       = var.log_id
  state                        = var.state

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
  value       = data.oci_logging_unified_agent_configurations.this.id
}

output "unified_agent_configuration_collection" {
  description = "returns a list of object"
  value       = data.oci_logging_unified_agent_configurations.this.unified_agent_configuration_collection
}

output "this" {
  value = oci_logging_unified_agent_configurations.this
}
```

[top](#index)