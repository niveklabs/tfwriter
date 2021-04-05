# scaleway_baremetal_offer

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_baremetal_offer" {
  source = "./modules/scaleway/d/scaleway_baremetal_offer"

  # include_disabled - (optional) is a type of bool
  include_disabled = null
  # name - (optional) is a type of string
  name = null
  # offer_id - (optional) is a type of string
  offer_id = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "include_disabled" {
  description = "(optional) - Include disabled offers"
  type        = bool
  default     = null
}

variable "name" {
  description = "(optional) - Exact name of the desired offer"
  type        = string
  default     = null
}

variable "offer_id" {
  description = "(optional) - ID of the desired offer"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_baremetal_offer" "this" {
  include_disabled = var.include_disabled
  name             = var.name
  offer_id         = var.offer_id
  zone             = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "bandwidth" {
  description = "returns a number"
  value       = data.scaleway_baremetal_offer.this.bandwidth
}

output "commercial_range" {
  description = "returns a string"
  value       = data.scaleway_baremetal_offer.this.commercial_range
}

output "cpu" {
  description = "returns a list of object"
  value       = data.scaleway_baremetal_offer.this.cpu
}

output "disk" {
  description = "returns a list of object"
  value       = data.scaleway_baremetal_offer.this.disk
}

output "id" {
  description = "returns a string"
  value       = data.scaleway_baremetal_offer.this.id
}

output "memory" {
  description = "returns a list of object"
  value       = data.scaleway_baremetal_offer.this.memory
}

output "stock" {
  description = "returns a string"
  value       = data.scaleway_baremetal_offer.this.stock
}

output "zone" {
  description = "returns a string"
  value       = data.scaleway_baremetal_offer.this.zone
}

output "this" {
  value = scaleway_baremetal_offer.this
}
```

[top](#index)