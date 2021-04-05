# scaleway_vpc_private_network

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
module "scaleway_vpc_private_network" {
  source = "./modules/scaleway/d/scaleway_vpc_private_network"

  # name - (optional) is a type of string
  name = null
  # private_network_id - (optional) is a type of string
  private_network_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - The name of the private network"
  type        = string
  default     = null
}

variable "private_network_id" {
  description = "(optional) - The ID of the private network"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_vpc_private_network" "this" {
  name               = var.name
  private_network_id = var.private_network_id
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = data.scaleway_vpc_private_network.this.created_at
}

output "id" {
  description = "returns a string"
  value       = data.scaleway_vpc_private_network.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = data.scaleway_vpc_private_network.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = data.scaleway_vpc_private_network.this.project_id
}

output "tags" {
  description = "returns a list of string"
  value       = data.scaleway_vpc_private_network.this.tags
}

output "updated_at" {
  description = "returns a string"
  value       = data.scaleway_vpc_private_network.this.updated_at
}

output "zone" {
  description = "returns a string"
  value       = data.scaleway_vpc_private_network.this.zone
}

output "this" {
  value = scaleway_vpc_private_network.this
}
```

[top](#index)