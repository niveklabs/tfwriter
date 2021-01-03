# packet_organization

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
module "packet_organization" {
  source = "./modules/packet/d/packet_organization"

  # name - (optional) is a type of string
  name = null
  # organization_id - (optional) is a type of string
  organization_id = null
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

variable "organization_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "packet_organization" "this" {
  name            = var.name
  organization_id = var.organization_id
}
```

[top](#index)

### Outputs

```terraform
output "description" {
  description = "returns a string"
  value       = data.packet_organization.this.description
}

output "id" {
  description = "returns a string"
  value       = data.packet_organization.this.id
}

output "logo" {
  description = "returns a string"
  value       = data.packet_organization.this.logo
}

output "name" {
  description = "returns a string"
  value       = data.packet_organization.this.name
}

output "organization_id" {
  description = "returns a string"
  value       = data.packet_organization.this.organization_id
}

output "project_ids" {
  description = "returns a list of string"
  value       = data.packet_organization.this.project_ids
}

output "twitter" {
  description = "returns a string"
  value       = data.packet_organization.this.twitter
}

output "website" {
  description = "returns a string"
  value       = data.packet_organization.this.website
}

output "this" {
  value = packet_organization.this
}
```

[top](#index)