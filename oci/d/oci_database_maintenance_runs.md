# oci_database_maintenance_runs

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
module "oci_database_maintenance_runs" {
  source = "./modules/oci/d/oci_database_maintenance_runs"

  # availability_domain - (optional) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # maintenance_type - (optional) is a type of string
  maintenance_type = null
  # state - (optional) is a type of string
  state = null
  # target_resource_id - (optional) is a type of string
  target_resource_id = null
  # target_resource_type - (optional) is a type of string
  target_resource_type = null

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
variable "availability_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "maintenance_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_resource_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "target_resource_type" {
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
data "oci_database_maintenance_runs" "this" {
  availability_domain  = var.availability_domain
  compartment_id       = var.compartment_id
  maintenance_type     = var.maintenance_type
  state                = var.state
  target_resource_id   = var.target_resource_id
  target_resource_type = var.target_resource_type

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
  value       = data.oci_database_maintenance_runs.this.id
}

output "maintenance_runs" {
  description = "returns a list of object"
  value       = data.oci_database_maintenance_runs.this.maintenance_runs
}

output "this" {
  value = oci_database_maintenance_runs.this
}
```

[top](#index)