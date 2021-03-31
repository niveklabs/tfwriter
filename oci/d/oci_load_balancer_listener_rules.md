# oci_load_balancer_listener_rules

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
module "oci_load_balancer_listener_rules" {
  source = "./modules/oci/d/oci_load_balancer_listener_rules"

  # listener_name - (required) is a type of string
  listener_name = null
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
variable "listener_name" {
  description = "(required)"
  type        = string
}

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
data "oci_load_balancer_listener_rules" "this" {
  listener_name    = var.listener_name
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
output "id" {
  description = "returns a string"
  value       = data.oci_load_balancer_listener_rules.this.id
}

output "listener_rules" {
  description = "returns a list of object"
  value       = data.oci_load_balancer_listener_rules.this.listener_rules
}

output "this" {
  value = oci_load_balancer_listener_rules.this
}
```

[top](#index)