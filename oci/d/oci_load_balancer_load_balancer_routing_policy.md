# oci_load_balancer_load_balancer_routing_policy

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
    oci = ">= 4.20.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_load_balancer_load_balancer_routing_policy" {
  source = "./modules/oci/d/oci_load_balancer_load_balancer_routing_policy"

  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
  # routing_policy_name - (required) is a type of string
  routing_policy_name = null
}
```

[top](#index)

### Variables

```terraform
variable "load_balancer_id" {
  description = "(required)"
  type        = string
}

variable "routing_policy_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_load_balancer_load_balancer_routing_policy" "this" {
  load_balancer_id    = var.load_balancer_id
  routing_policy_name = var.routing_policy_name
}
```

[top](#index)

### Outputs

```terraform
output "condition_language_version" {
  description = "returns a string"
  value       = data.oci_load_balancer_load_balancer_routing_policy.this.condition_language_version
}

output "id" {
  description = "returns a string"
  value       = data.oci_load_balancer_load_balancer_routing_policy.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_load_balancer_load_balancer_routing_policy.this.name
}

output "rules" {
  description = "returns a list of object"
  value       = data.oci_load_balancer_load_balancer_routing_policy.this.rules
}

output "state" {
  description = "returns a string"
  value       = data.oci_load_balancer_load_balancer_routing_policy.this.state
}

output "this" {
  value = oci_load_balancer_load_balancer_routing_policy.this
}
```

[top](#index)