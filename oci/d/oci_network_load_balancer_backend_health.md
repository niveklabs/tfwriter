# oci_network_load_balancer_backend_health

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
module "oci_network_load_balancer_backend_health" {
  source = "./modules/oci/d/oci_network_load_balancer_backend_health"

  # backend_name - (required) is a type of string
  backend_name = null
  # backend_set_name - (required) is a type of string
  backend_set_name = null
  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = null
}
```

[top](#index)

### Variables

```terraform
variable "backend_name" {
  description = "(required)"
  type        = string
}

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
data "oci_network_load_balancer_backend_health" "this" {
  backend_name             = var.backend_name
  backend_set_name         = var.backend_set_name
  network_load_balancer_id = var.network_load_balancer_id
}
```

[top](#index)

### Outputs

```terraform
output "health_check_results" {
  description = "returns a list of object"
  value       = data.oci_network_load_balancer_backend_health.this.health_check_results
}

output "id" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_backend_health.this.id
}

output "status" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_backend_health.this.status
}

output "this" {
  value = oci_network_load_balancer_backend_health.this
}
```

[top](#index)