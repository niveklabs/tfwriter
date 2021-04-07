# oci_mysql_mysql_db_systems

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
module "oci_mysql_mysql_db_systems" {
  source = "./modules/oci/d/oci_mysql_mysql_db_systems"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # configuration_id - (optional) is a type of string
  configuration_id = null
  # db_system_id - (optional) is a type of string
  db_system_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # is_analytics_cluster_attached - (optional) is a type of bool
  is_analytics_cluster_attached = null
  # is_heat_wave_cluster_attached - (optional) is a type of bool
  is_heat_wave_cluster_attached = null
  # is_up_to_date - (optional) is a type of bool
  is_up_to_date = null
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

variable "configuration_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "db_system_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "is_analytics_cluster_attached" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_heat_wave_cluster_attached" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "is_up_to_date" {
  description = "(optional)"
  type        = bool
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
data "oci_mysql_mysql_db_systems" "this" {
  compartment_id                = var.compartment_id
  configuration_id              = var.configuration_id
  db_system_id                  = var.db_system_id
  display_name                  = var.display_name
  is_analytics_cluster_attached = var.is_analytics_cluster_attached
  is_heat_wave_cluster_attached = var.is_heat_wave_cluster_attached
  is_up_to_date                 = var.is_up_to_date
  state                         = var.state

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
output "db_systems" {
  description = "returns a list of object"
  value       = data.oci_mysql_mysql_db_systems.this.db_systems
}

output "id" {
  description = "returns a string"
  value       = data.oci_mysql_mysql_db_systems.this.id
}

output "this" {
  value = oci_mysql_mysql_db_systems.this
}
```

[top](#index)