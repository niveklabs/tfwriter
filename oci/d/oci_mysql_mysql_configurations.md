# oci_mysql_mysql_configurations

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
module "oci_mysql_mysql_configurations" {
  source = "./modules/oci/d/oci_mysql_mysql_configurations"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # configuration_id - (optional) is a type of string
  configuration_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # shape_name - (optional) is a type of string
  shape_name = null
  # state - (optional) is a type of string
  state = null
  # type - (optional) is a type of list of string
  type = []

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

variable "configuration_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "shape_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = list(string)
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
data "oci_mysql_mysql_configurations" "this" {
  compartment_id   = var.compartment_id
  configuration_id = var.configuration_id
  display_name     = var.display_name
  shape_name       = var.shape_name
  state            = var.state
  type             = var.type

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
output "configurations" {
  description = "returns a list of object"
  value       = data.oci_mysql_mysql_configurations.this.configurations
}

output "id" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_configurations.this.id
}

output "this" {
  value = oci_mysql_mysql_configurations.this
}
```

[top](#index)