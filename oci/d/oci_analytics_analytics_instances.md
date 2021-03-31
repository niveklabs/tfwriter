# oci_analytics_analytics_instances

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
    oci = ">= 4.19.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_analytics_analytics_instances" {
  source = "./modules/oci/d/oci_analytics_analytics_instances"

  # capacity_type - (optional) is a type of string
  capacity_type = null
  # compartment_id - (required) is a type of string
  compartment_id = null
  # feature_set - (optional) is a type of string
  feature_set = null
  # name - (optional) is a type of string
  name = null
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
variable "capacity_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "compartment_id" {
  description = "(required)"
  type        = string
}

variable "feature_set" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
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
data "oci_analytics_analytics_instances" "this" {
  capacity_type  = var.capacity_type
  compartment_id = var.compartment_id
  feature_set    = var.feature_set
  name           = var.name
  state          = var.state

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
output "analytics_instances" {
  description = "returns a list of object"
  value       = data.oci_analytics_analytics_instances.this.analytics_instances
}

output "id" {
  description = "returns a string"
  value       = data.oci_analytics_analytics_instances.this.id
}

output "this" {
  value = oci_analytics_analytics_instances.this
}
```

[top](#index)