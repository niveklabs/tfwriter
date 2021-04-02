# oci_identity_idp_group_mappings

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
module "oci_identity_idp_group_mappings" {
  source = "./modules/oci/d/oci_identity_idp_group_mappings"

  # identity_provider_id - (required) is a type of string
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
variable "identity_provider_id" {
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
data "oci_identity_idp_group_mappings" "this" {
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
  value       = data.oci_identity_idp_group_mappings.this.id
}

output "idp_group_mappings" {
  description = "returns a list of object"
  value       = data.oci_identity_idp_group_mappings.this.idp_group_mappings
}

output "this" {
  value = oci_identity_idp_group_mappings.this
}
```

[top](#index)