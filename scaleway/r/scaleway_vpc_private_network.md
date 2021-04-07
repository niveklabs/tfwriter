# scaleway_vpc_private_network

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/scaleway/r/scaleway_vpc_private_network"

  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
  # tags - (optional) is a type of list of string
  tags = []
  # zone - (optional) is a type of string
  zone = null
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

variable "project_id" {
  description = "(optional) - The project_id you want to attach the resource to"
  type        = string
  default     = null
}

variable "tags" {
  description = "(optional) - The tags associated with private network"
  type        = list(string)
  default     = null
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "scaleway_vpc_private_network" "this" {
  # name - (optional) is a type of string
  name = var.name
  # project_id - (optional) is a type of string
  project_id = var.project_id
  # tags - (optional) is a type of list of string
  tags = var.tags
  # zone - (optional) is a type of string
  zone = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "created_at" {
  description = "returns a string"
  value       = scaleway_vpc_private_network.this.created_at
}

output "id" {
  description = "returns a string"
  value       = scaleway_vpc_private_network.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = scaleway_vpc_private_network.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = scaleway_vpc_private_network.this.project_id
}

output "updated_at" {
  description = "returns a string"
  value       = scaleway_vpc_private_network.this.updated_at
}

output "zone" {
  description = "returns a string"
  value       = scaleway_vpc_private_network.this.zone
}

output "this" {
  value = scaleway_vpc_private_network.this
}
```

[top](#index)