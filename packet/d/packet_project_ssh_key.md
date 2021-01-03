# packet_project_ssh_key

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
module "packet_project_ssh_key" {
  source = "./modules/packet/d/packet_project_ssh_key"

  # project_id - (required) is a type of string
  project_id = null
  # search - (optional) is a type of string
  search = null
}
```

[top](#index)

### Variables

```terraform
variable "project_id" {
  description = "(required) - The Equinix Metal project id of the Equinix Metal SSH Key"
  type        = string
}

variable "search" {
  description = "(optional) - The name, fingerprint, id, or public_key of the SSH Key to search for in the Equinix Metal project"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "packet_project_ssh_key" "this" {
  project_id = var.project_id
  search     = var.search
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = data.packet_project_ssh_key.this.created
}

output "fingerprint" {
  description = "returns a string"
  value       = data.packet_project_ssh_key.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = data.packet_project_ssh_key.this.id
}

output "name" {
  description = "returns a string"
  value       = data.packet_project_ssh_key.this.name
}

output "owner_id" {
  description = "returns a string"
  value       = data.packet_project_ssh_key.this.owner_id
}

output "public_key" {
  description = "returns a string"
  value       = data.packet_project_ssh_key.this.public_key
}

output "updated" {
  description = "returns a string"
  value       = data.packet_project_ssh_key.this.updated
}

output "this" {
  value = packet_project_ssh_key.this
}
```

[top](#index)