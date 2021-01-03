# oci_audit_events

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
module "oci_audit_events" {
  source = "./modules/oci/d/oci_audit_events"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # end_time - (required) is a type of string
  end_time = null
  # start_time - (required) is a type of string
  start_time = null

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

variable "end_time" {
  description = "(required)"
  type        = string
}

variable "start_time" {
  description = "(required)"
  type        = string
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
data "oci_audit_events" "this" {
  compartment_id = var.compartment_id
  end_time       = var.end_time
  start_time     = var.start_time

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
output "audit_events" {
  description = "returns a list of object"
  value       = data.oci_audit_events.this.audit_events
}

output "id" {
  description = "returns a string"
  value       = data.oci_audit_events.this.id
}

output "this" {
  value = oci_audit_events.this
}
```

[top](#index)