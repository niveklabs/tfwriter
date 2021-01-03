# oci_identity_users

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
module "oci_identity_users" {
  source = "./modules/oci/d/oci_identity_users"

  # compartment_id - (required) is a type of string
  compartment_id = null
  # external_identifier - (optional) is a type of string
  external_identifier = null
  # identity_provider_id - (optional) is a type of string
  identity_provider_id = null

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

variable "external_identifier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "identity_provider_id" {
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
data "oci_identity_users" "this" {
  compartment_id       = var.compartment_id
  external_identifier  = var.external_identifier
  identity_provider_id = var.identity_provider_id

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
  value       = data.oci_identity_users.this.id
}

output "users" {
  description = "returns a list of object"
  value       = data.oci_identity_users.this.users
}

output "this" {
  value = oci_identity_users.this
}
```

[top](#index)