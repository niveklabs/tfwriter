# oci_identity_region_subscriptions

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
module "oci_identity_region_subscriptions" {
  source = "./modules/oci/d/oci_identity_region_subscriptions"

  # tenancy_id - (required) is a type of string
  tenancy_id = null

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
variable "tenancy_id" {
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
data "oci_identity_region_subscriptions" "this" {
  tenancy_id = var.tenancy_id

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
  value       = data.oci_identity_region_subscriptions.this.id
}

output "region_subscriptions" {
  description = "returns a list of object"
  value       = data.oci_identity_region_subscriptions.this.region_subscriptions
}

output "this" {
  value = oci_identity_region_subscriptions.this
}
```

[top](#index)