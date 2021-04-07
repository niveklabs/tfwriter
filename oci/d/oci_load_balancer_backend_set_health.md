# oci_load_balancer_backend_set_health

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
module "oci_load_balancer_backend_set_health" {
  source = "./modules/oci/d/oci_load_balancer_backend_set_health"

  # backend_set_name - (required) is a type of string
  backend_set_name = null
  # load_balancer_id - (required) is a type of string
  load_balancer_id = null
}
```

[top](#index)

### Variables

```terraform
variable "backend_set_name" {
  description = "(required)"
  type        = string
}

variable "load_balancer_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_load_balancer_backend_set_health" "this" {
  backend_set_name = var.backend_set_name
  load_balancer_id = var.load_balancer_id
}
```

[top](#index)

### Outputs

```terraform
output "critical_state_backend_names" {
  description = "returns a list of string"
  value       = data.oci_load_balancer_backend_set_health.this.critical_state_backend_names
}

output "id" {
  description = "returns a string"
  value       = data.oci_load_balancer_backend_set_health.this.id
}

output "status" {
  description = "returns a string"
  value       = data.oci_load_balancer_backend_set_health.this.status
}

output "total_backend_count" {
  description = "returns a number"
  value       = data.oci_load_balancer_backend_set_health.this.total_backend_count
}

output "unknown_state_backend_names" {
  description = "returns a list of string"
  value       = data.oci_load_balancer_backend_set_health.this.unknown_state_backend_names
}

output "warning_state_backend_names" {
  description = "returns a list of string"
  value       = data.oci_load_balancer_backend_set_health.this.warning_state_backend_names
}

output "this" {
  value = oci_load_balancer_backend_set_health.this
}
```

[top](#index)