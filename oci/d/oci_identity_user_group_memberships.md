# oci_identity_user_group_memberships

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
module "oci_identity_user_group_memberships" {
  source = "./modules/oci/d/oci_identity_user_group_memberships"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # group_id - (optional) is a type of string
  group_id = null
  # user_id - (optional) is a type of string
  user_id = null

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

variable "group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_id" {
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
data "oci_identity_user_group_memberships" "this" {
  compartment_id = var.compartment_id
  group_id       = var.group_id
  user_id        = var.user_id

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
  value       = data.oci_identity_user_group_memberships.this.id
}

output "memberships" {
  description = "returns a list of object"
  value       = data.oci_identity_user_group_memberships.this.memberships
}

output "this" {
  value = oci_identity_user_group_memberships.this
}
```

[top](#index)