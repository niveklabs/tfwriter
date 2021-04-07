# oci_identity_tag_namespaces

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
module "oci_identity_tag_namespaces" {
  source = "./modules/oci/d/oci_identity_tag_namespaces"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # include_subcompartments - (optional) is a type of bool
  include_subcompartments = null
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

variable "include_subcompartments" {
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
data "oci_identity_tag_namespaces" "this" {
  # compartment_id - (required) is a type of string
  compartment_id = var.compartment_id
  # include_subcompartments - (optional) is a type of bool
  include_subcompartments = var.include_subcompartments
  # state - (optional) is a type of string
  state = var.state

  dynamic "filter" {
    for_each = var.filter
    content {
      # name - (required) is a type of string
      name = filter.value["name"]
      # regex - (optional) is a type of bool
      regex = filter.value["regex"]
      # values - (required) is a type of list of string
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
  value       = data.oci_identity_tag_namespaces.this.id
}

output "tag_namespaces" {
  description = "returns a list of object"
  value       = data.oci_identity_tag_namespaces.this.tag_namespaces
}

output "this" {
  value = oci_identity_tag_namespaces.this
}
```

[top](#index)