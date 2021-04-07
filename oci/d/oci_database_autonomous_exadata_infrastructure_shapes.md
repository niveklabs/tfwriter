# oci_database_autonomous_exadata_infrastructure_shapes

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
module "oci_database_autonomous_exadata_infrastructure_shapes" {
  source = "./modules/oci/d/oci_database_autonomous_exadata_infrastructure_shapes"

  # availability_domain - (required) is a type of string
  availability_domain = null
  # compartment_id - (required) is a type of string
  compartment_id = null

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
variable "availability_domain" {
  description = "(required)"
  type        = string
}

variable "compartment_id" {
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
data "oci_database_autonomous_exadata_infrastructure_shapes" "this" {
  availability_domain = var.availability_domain
  compartment_id      = var.compartment_id

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
output "autonomous_exadata_infrastructure_shapes" {
  description = "returns a list of object"
  value       = data.oci_database_autonomous_exadata_infrastructure_shapes.this.autonomous_exadata_infrastructure_shapes
}

output "id" {
  description = "returns a string"
  value       = data.oci_database_autonomous_exadata_infrastructure_shapes.this.id
}

output "this" {
  value = oci_database_autonomous_exadata_infrastructure_shapes.this
}
```

[top](#index)