# oci_identity_identity_provider_groups

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
module "oci_identity_identity_provider_groups" {
  source = "./modules/oci/d/oci_identity_identity_provider_groups"

  # identity_provider_id - (required) is a type of string
  identity_provider_id = null
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
variable "identity_provider_id" {
  description = "(required)"
  type        = string
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
data "oci_identity_identity_provider_groups" "this" {
  identity_provider_id = var.identity_provider_id
  name                 = var.name
  state                = var.state

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
  value       = data.oci_identity_identity_provider_groups.this.id
}

output "identity_provider_groups" {
  description = "returns a list of object"
  value       = data.oci_identity_identity_provider_groups.this.identity_provider_groups
}

output "this" {
  value = oci_identity_identity_provider_groups.this
}
```

[top](#index)