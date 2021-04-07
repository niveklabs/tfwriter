# oci_kms_vault_replicas

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
module "oci_kms_vault_replicas" {
  source = "./modules/oci/d/oci_kms_vault_replicas"

  # vault_id - (required) is a type of string
  vault_id = null

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
variable "vault_id" {
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
data "oci_kms_vault_replicas" "this" {
  vault_id = var.vault_id

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
  value       = data.oci_kms_vault_replicas.this.id
}

output "vault_replicas" {
  description = "returns a list of object"
  value       = data.oci_kms_vault_replicas.this.vault_replicas
}

output "this" {
  value = oci_kms_vault_replicas.this
}
```

[top](#index)