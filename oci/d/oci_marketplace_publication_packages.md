# oci_marketplace_publication_packages

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
module "oci_marketplace_publication_packages" {
  source = "./modules/oci/d/oci_marketplace_publication_packages"

  # package_type - (optional) is a type of string
  package_type = null
  # package_version - (optional) is a type of string
  package_version = null
  # publication_id - (required) is a type of string
  publication_id = null

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
variable "package_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "package_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "publication_id" {
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
data "oci_marketplace_publication_packages" "this" {
  # package_type - (optional) is a type of string
  package_type = var.package_type
  # package_version - (optional) is a type of string
  package_version = var.package_version
  # publication_id - (required) is a type of string
  publication_id = var.publication_id

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
  value       = data.oci_marketplace_publication_packages.this.id
}

output "publication_packages" {
  description = "returns a list of object"
  value       = data.oci_marketplace_publication_packages.this.publication_packages
}

output "this" {
  value = oci_marketplace_publication_packages.this
}
```

[top](#index)