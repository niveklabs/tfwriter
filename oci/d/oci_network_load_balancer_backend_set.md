# oci_network_load_balancer_backend_set

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
module "oci_network_load_balancer_backend_set" {
  source = "./modules/oci/d/oci_network_load_balancer_backend_set"

  # backend_set_name - (required) is a type of string
  backend_set_name = null
  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = null
}
```

[top](#index)

### Variables

```terraform
variable "backend_set_name" {
  description = "(required)"
  type        = string
}

variable "network_load_balancer_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_network_load_balancer_backend_set" "this" {
  backend_set_name         = var.backend_set_name
  network_load_balancer_id = var.network_load_balancer_id
}
```

[top](#index)

### Outputs

```terraform
output "backends" {
  description = "returns a list of object"
  value       = data.oci_network_load_balancer_backend_set.this.backends
}

output "health_checker" {
  description = "returns a list of object"
  value       = data.oci_network_load_balancer_backend_set.this.health_checker
}

output "id" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_backend_set.this.id
}

output "is_preserve_source" {
  description = "returns a bool"
  value       = data.oci_network_load_balancer_backend_set.this.is_preserve_source
}

output "name" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_backend_set.this.name
}

output "policy" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_backend_set.this.policy
}

output "this" {
  value = oci_network_load_balancer_backend_set.this
}
```

[top](#index)