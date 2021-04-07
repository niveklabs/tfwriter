# oci_identity_tag_defaults

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
module "oci_identity_tag_defaults" {
  source = "./modules/oci/d/oci_identity_tag_defaults"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # state - (optional) is a type of string
  state = null
  # tag_definition_id - (optional) is a type of string
  tag_definition_id = null

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
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tag_definition_id" {
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
data "oci_identity_tag_defaults" "this" {
  compartment_id    = var.compartment_id
  state             = var.state
  tag_definition_id = var.tag_definition_id

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
  value       = data.oci_identity_tag_defaults.this.id
}

output "tag_defaults" {
  description = "returns a list of object"
  value       = data.oci_identity_tag_defaults.this.tag_defaults
}

output "this" {
  value = oci_identity_tag_defaults.this
}
```

[top](#index)