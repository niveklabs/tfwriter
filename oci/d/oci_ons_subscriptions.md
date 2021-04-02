# oci_ons_subscriptions

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
module "oci_ons_subscriptions" {
  source = "./modules/oci/d/oci_ons_subscriptions"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # topic_id - (optional) is a type of string
  topic_id = null

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

variable "topic_id" {
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
data "oci_ons_subscriptions" "this" {
  compartment_id = var.compartment_id
  topic_id       = var.topic_id

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
  value       = data.oci_ons_subscriptions.this.id
}

output "subscriptions" {
  description = "returns a list of object"
  value       = data.oci_ons_subscriptions.this.subscriptions
}

output "this" {
  value = oci_ons_subscriptions.this
}
```

[top](#index)