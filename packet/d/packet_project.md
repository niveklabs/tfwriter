# packet_project

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    packet = ">= 3.2.1"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "packet_project" {
  source = "./modules/packet/d/packet_project"

  # name - (optional) is a type of string
  name = null
  # project_id - (optional) is a type of string
  project_id = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "project_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "packet_project" "this" {
  name       = var.name
  project_id = var.project_id
}
```

[top](#index)

### Outputs

```terraform
output "backend_transfer" {
  description = "returns a bool"
  value       = data.packet_project.this.backend_transfer
}

output "bgp_config" {
  description = "returns a list of object"
  value       = data.packet_project.this.bgp_config
}

output "created" {
  description = "returns a string"
  value       = data.packet_project.this.created
}

output "id" {
  description = "returns a string"
  value       = data.packet_project.this.id
}

output "name" {
  description = "returns a string"
  value       = data.packet_project.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = data.packet_project.this.organization_id
}

output "payment_method_id" {
  description = "returns a string"
  value       = data.packet_project.this.payment_method_id
}

output "project_id" {
  description = "returns a string"
  value       = data.packet_project.this.project_id
}

output "updated" {
  description = "returns a string"
  value       = data.packet_project.this.updated
}

output "user_ids" {
  description = "returns a list of string"
  value       = data.packet_project.this.user_ids
}

output "this" {
  value = packet_project.this
}
```

[top](#index)