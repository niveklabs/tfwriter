# fortios_router_policy6

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_router_policy6" {
  source = "./modules/fortios/d/fortios_router_policy6"

  # seq_num - (required) is a type of number
  seq_num = null
}
```

[top](#index)

### Variables

```terraform
variable "seq_num" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "fortios_router_policy6" "this" {
  # seq_num - (required) is a type of number
  seq_num = var.seq_num
}
```

[top](#index)

### Outputs

```terraform
output "comments" {
  description = "returns a string"
  value       = data.fortios_router_policy6.this.comments
}

output "dst" {
  description = "returns a string"
  value       = data.fortios_router_policy6.this.dst
}

output "end_port" {
  description = "returns a number"
  value       = data.fortios_router_policy6.this.end_port
}

output "gateway" {
  description = "returns a string"
  value       = data.fortios_router_policy6.this.gateway
}

output "id" {
  description = "returns a string"
  value       = data.fortios_router_policy6.this.id
}

output "input_device" {
  description = "returns a string"
  value       = data.fortios_router_policy6.this.input_device
}

output "output_device" {
  description = "returns a string"
  value       = data.fortios_router_policy6.this.output_device
}

output "protocol" {
  description = "returns a number"
  value       = data.fortios_router_policy6.this.protocol
}

output "src" {
  description = "returns a string"
  value       = data.fortios_router_policy6.this.src
}

output "start_port" {
  description = "returns a number"
  value       = data.fortios_router_policy6.this.start_port
}

output "status" {
  description = "returns a string"
  value       = data.fortios_router_policy6.this.status
}

output "tos" {
  description = "returns a string"
  value       = data.fortios_router_policy6.this.tos
}

output "tos_mask" {
  description = "returns a string"
  value       = data.fortios_router_policy6.this.tos_mask
}

output "this" {
  value = fortios_router_policy6.this
}
```

[top](#index)