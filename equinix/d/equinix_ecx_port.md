# equinix_ecx_port

[back](../equinix.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    equinix = ">= 1.1.0-beta"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "equinix_ecx_port" {
  source = "./modules/equinix/d/equinix_ecx_port"

  # name - (required) is a type of string
  name = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required) - Name of the port"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "equinix_ecx_port" "this" {
  # name - (required) is a type of string
  name = var.name
}
```

[top](#index)

### Outputs

```terraform
output "bandwidth" {
  description = "returns a string"
  value       = data.equinix_ecx_port.this.bandwidth
}

output "buyout" {
  description = "returns a bool"
  value       = data.equinix_ecx_port.this.buyout
}

output "encapsulation" {
  description = "returns a string"
  value       = data.equinix_ecx_port.this.encapsulation
}

output "ibx" {
  description = "returns a string"
  value       = data.equinix_ecx_port.this.ibx
}

output "id" {
  description = "returns a string"
  value       = data.equinix_ecx_port.this.id
}

output "metro_code" {
  description = "returns a string"
  value       = data.equinix_ecx_port.this.metro_code
}

output "priority" {
  description = "returns a string"
  value       = data.equinix_ecx_port.this.priority
}

output "region" {
  description = "returns a string"
  value       = data.equinix_ecx_port.this.region
}

output "status" {
  description = "returns a string"
  value       = data.equinix_ecx_port.this.status
}

output "uuid" {
  description = "returns a string"
  value       = data.equinix_ecx_port.this.uuid
}

output "this" {
  value = equinix_ecx_port.this
}
```

[top](#index)