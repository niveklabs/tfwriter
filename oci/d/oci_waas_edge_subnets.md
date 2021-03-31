# oci_waas_edge_subnets

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
module "oci_waas_edge_subnets" {
  source = "./modules/oci/d/oci_waas_edge_subnets"


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
data "oci_waas_edge_subnets" "this" {

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
output "edge_subnets" {
  description = "returns a list of object"
  value       = data.oci_waas_edge_subnets.this.edge_subnets
}

output "id" {
  description = "returns a string"
  value       = data.oci_waas_edge_subnets.this.id
}

output "this" {
  value = oci_waas_edge_subnets.this
}
```

[top](#index)