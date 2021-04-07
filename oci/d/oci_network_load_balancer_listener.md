# oci_network_load_balancer_listener

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
module "oci_network_load_balancer_listener" {
  source = "./modules/oci/d/oci_network_load_balancer_listener"

  # listener_name - (required) is a type of string
  listener_name = null
  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = null
}
```

[top](#index)

### Variables

```terraform
variable "listener_name" {
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
data "oci_network_load_balancer_listener" "this" {
  # listener_name - (required) is a type of string
  listener_name = var.listener_name
  # network_load_balancer_id - (required) is a type of string
  network_load_balancer_id = var.network_load_balancer_id
}
```

[top](#index)

### Outputs

```terraform
output "default_backend_set_name" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_listener.this.default_backend_set_name
}

output "id" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_listener.this.id
}

output "name" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_listener.this.name
}

output "port" {
  description = "returns a number"
  value       = data.oci_network_load_balancer_listener.this.port
}

output "protocol" {
  description = "returns a string"
  value       = data.oci_network_load_balancer_listener.this.protocol
}

output "this" {
  value = oci_network_load_balancer_listener.this
}
```

[top](#index)