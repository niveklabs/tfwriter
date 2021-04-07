# oci_kms_key_versions

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
module "oci_kms_key_versions" {
  source = "./modules/oci/d/oci_kms_key_versions"

  # key_id - (required) is a type of string
  key_id = null
  # management_endpoint - (required) is a type of string
  management_endpoint = null

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
variable "key_id" {
  description = "(required)"
  type        = string
}

variable "management_endpoint" {
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
data "oci_kms_key_versions" "this" {
  key_id              = var.key_id
  management_endpoint = var.management_endpoint

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
  value       = data.oci_kms_key_versions.this.id
}

output "key_versions" {
  description = "returns a list of object"
  value       = data.oci_kms_key_versions.this.key_versions
}

output "this" {
  value = oci_kms_key_versions.this
}
```

[top](#index)