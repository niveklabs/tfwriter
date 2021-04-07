# exoscale_nlb

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
module "exoscale_nlb" {
  source = "./modules/exoscale/d/exoscale_nlb"

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
  description = "(optional) - Name of the Network Load Balancer"
  type        = string
  default     = null
}

variable "zone" {
  description = "(required) - Zone of the Network Load Balancer"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "exoscale_nlb" "this" {
  # name - (optional) is a type of string
  name = var.name
  # zone - (required) is a type of string
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.exoscale_nlb.this.created_at
}

output "description" {
  description = "returns a string"
  value       = data.exoscale_nlb.this.description
}

output "id" {
  description = "returns a string"
  value       = data.exoscale_nlb.this.id
}

output "ip_address" {
  description = "returns a string"
  value       = data.exoscale_nlb.this.ip_address
}

output "state" {
  description = "returns a string"
  value       = data.exoscale_nlb.this.state
}

output "this" {
  value = exoscale_nlb.this
}
```

[top](#index)