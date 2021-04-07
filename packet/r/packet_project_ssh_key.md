# packet_project_ssh_key

[back](../packet.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
  source = "./modules/packet/r/packet_project_ssh_key"

  # name - (required) is a type of string
  name = null
  # project_id - (required) is a type of string
  project_id = null
  # public_key - (required) is a type of string
  public_key = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(required)"
  type        = string
}

variable "project_id" {
  description = "(required)"
  type        = string
}

variable "public_key" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "packet_project_ssh_key" "this" {
  # name - (required) is a type of string
  name = var.name
  # project_id - (required) is a type of string
  project_id = var.project_id
  # public_key - (required) is a type of string
  public_key = var.public_key
}
```

[top](#index)

### Outputs

```terraform
output "created" {
  description = "returns a string"
  value       = packet_project_ssh_key.this.created
}

output "fingerprint" {
  description = "returns a string"
  value       = packet_project_ssh_key.this.fingerprint
}

output "id" {
  description = "returns a string"
  value       = packet_project_ssh_key.this.id
}

output "owner_id" {
  description = "returns a string"
  value       = packet_project_ssh_key.this.owner_id
}

output "updated" {
  description = "returns a string"
  value       = packet_project_ssh_key.this.updated
}

output "this" {
  value = packet_project_ssh_key.this
}
```

[top](#index)