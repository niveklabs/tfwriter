# oci_identity_customer_secret_keys

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
module "oci_identity_customer_secret_keys" {
  source = "./modules/oci/d/oci_identity_customer_secret_keys"

  # user_id - (required) is a type of string
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
variable "user_id" {
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
data "oci_identity_customer_secret_keys" "this" {
  user_id = var.user_id

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
output "customer_secret_keys" {
  description = "returns a list of object"
  value       = data.oci_identity_customer_secret_keys.this.customer_secret_keys
}

output "id" {
  description = "returns a string"
  value       = data.oci_identity_customer_secret_keys.this.id
}

output "this" {
  value = oci_identity_customer_secret_keys.this
}
```

[top](#index)