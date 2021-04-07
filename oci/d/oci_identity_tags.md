# oci_identity_tags

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
module "oci_identity_tags" {
  source = "./modules/oci/d/oci_identity_tags"

  # state - (optional) is a type of string
  state = null
  # tag_namespace_id - (required) is a type of string
  tag_namespace_id = null

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
variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tag_namespace_id" {
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
data "oci_identity_tags" "this" {
  # state - (optional) is a type of string
  state = var.state
  # tag_namespace_id - (required) is a type of string
  tag_namespace_id = var.tag_namespace_id

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
  value       = data.oci_identity_tags.this.id
}

output "tags" {
  description = "returns a list of object"
  value       = data.oci_identity_tags.this.tags
}

output "this" {
  value = oci_identity_tags.this
}
```

[top](#index)