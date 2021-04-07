# oci_health_checks_http_monitors

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
module "oci_health_checks_http_monitors" {
  source = "./modules/oci/d/oci_health_checks_http_monitors"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # home_region - (optional) is a type of string
  home_region = null

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

variable "home_region" {
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
data "oci_health_checks_http_monitors" "this" {
  compartment_id = var.compartment_id
  display_name   = var.display_name
  home_region    = var.home_region

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
output "http_monitors" {
  description = "returns a list of object"
  value       = data.oci_health_checks_http_monitors.this.http_monitors
}

output "id" {
  description = "returns a string"
  value       = data.oci_health_checks_http_monitors.this.id
}

output "this" {
  value = oci_health_checks_http_monitors.this
}
```

[top](#index)