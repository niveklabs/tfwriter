# exoscale_network

[back](../exoscale.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    exoscale = ">= 0.23.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "exoscale_network" {
  source = "./modules/exoscale/d/exoscale_network"

  # name - (optional) is a type of string
  name = null
  # zone - (required) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Name of the network"
  type        = string
  default     = null
}

variable "zone" {
  description = "(required) - Name of the zone"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "exoscale_network" "this" {
  name = var.name
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.exoscale_network.this.description
}

output "end_ip" {
  description = "returns a string"
  value       = data.exoscale_network.this.end_ip
}

output "id" {
  description = "returns a string"
  value       = data.exoscale_network.this.id
}

output "netmask" {
  description = "returns a string"
  value       = data.exoscale_network.this.netmask
}

output "start_ip" {
  description = "returns a string"
  value       = data.exoscale_network.this.start_ip
}

output "this" {
  value = exoscale_network.this
}
```

[top](#index)