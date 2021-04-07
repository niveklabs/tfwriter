# oci_load_balancer_rule_set

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
module "oci_load_balancer_rule_set" {
  source = "./modules/oci/d/oci_load_balancer_rule_set"

  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_load_balancer_rule_set" "this" {
  load_balancer_id = var.load_balancer_id
  name             = var.name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_load_balancer_rule_set.this.id
}

output "items" {
  description = "returns a list of object"
  value       = data.oci_load_balancer_rule_set.this.items
}

output "state" {
  description = "returns a string"
  value       = data.oci_load_balancer_rule_set.this.state
}

output "this" {
  value = oci_load_balancer_rule_set.this
}
```

[top](#index)