# oci_load_balancer_backendsets

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
module "oci_load_balancer_backendsets" {
  source = "./modules/oci/d/oci_load_balancer_backendsets"

  # load_balancer_id - (required) is a type of string
  load_balancer_id = null

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
variable "load_balancer_id" {
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
data "oci_load_balancer_backendsets" "this" {
  load_balancer_id = var.load_balancer_id

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
output "backendsets" {
  description = "returns a list of object"
  value       = data.oci_load_balancer_backendsets.this.backendsets
}

output "id" {
  description = "returns a string"
  value       = data.oci_load_balancer_backendsets.this.id
}

output "this" {
  value = oci_load_balancer_backendsets.this
}
```

[top](#index)