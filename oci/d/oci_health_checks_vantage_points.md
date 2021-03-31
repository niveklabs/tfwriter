# oci_health_checks_vantage_points

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
module "oci_health_checks_vantage_points" {
  source = "./modules/oci/d/oci_health_checks_vantage_points"

  # display_name - (optional) is a type of string
  display_name = null
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
variable "display_name" {
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
data "oci_health_checks_vantage_points" "this" {
  display_name = var.display_name
  name         = var.name

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
output "health_checks_vantage_points" {
  description = "returns a list of object"
  value       = data.oci_health_checks_vantage_points.this.health_checks_vantage_points
}

output "id" {
  description = "returns a string"
  value       = data.oci_health_checks_vantage_points.this.id
}

output "this" {
  value = oci_health_checks_vantage_points.this
}
```

[top](#index)