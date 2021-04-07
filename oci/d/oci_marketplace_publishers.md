# oci_marketplace_publishers

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
module "oci_marketplace_publishers" {
  source = "./modules/oci/d/oci_marketplace_publishers"

  # compartment_id - (optional) is a type of string
  compartment_id = null
  # publisher_id - (optional) is a type of string
  publisher_id = null

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
  description = "(optional)"
  type        = string
  default     = null
}

variable "publisher_id" {
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
data "oci_marketplace_publishers" "this" {
  compartment_id = var.compartment_id
  publisher_id   = var.publisher_id

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
  value       = data.oci_marketplace_publishers.this.id
}

output "publishers" {
  description = "returns a list of object"
  value       = data.oci_marketplace_publishers.this.publishers
}

output "this" {
  value = oci_marketplace_publishers.this
}
```

[top](#index)