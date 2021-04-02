# oci_osmanagement_managed_instances

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
module "oci_osmanagement_managed_instances" {
  source = "./modules/oci/d/oci_osmanagement_managed_instances"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # display_name - (optional) is a type of string
  display_name = null
  # os_family - (optional) is a type of string
  os_family = null

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

variable "os_family" {
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
data "oci_osmanagement_managed_instances" "this" {
  compartment_id = var.compartment_id
  display_name   = var.display_name
  os_family      = var.os_family

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
  value       = data.oci_osmanagement_managed_instances.this.id
}

output "managed_instances" {
  description = "returns a list of object"
  value       = data.oci_osmanagement_managed_instances.this.managed_instances
}

output "this" {
  value = oci_osmanagement_managed_instances.this
}
```

[top](#index)