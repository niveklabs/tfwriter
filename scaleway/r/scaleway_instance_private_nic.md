# scaleway_instance_private_nic

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
module "scaleway_instance_private_nic" {
  source = "./modules/scaleway/r/scaleway_instance_private_nic"

  # private_network_id - (required) is a type of string
  private_network_id = null
  # server_id - (required) is a type of string
  server_id = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "private_network_id" {
  description = "(required) - The private network ID"
  type        = string
}

variable "server_id" {
  description = "(required) - The server ID"
  type        = string
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
resource "scaleway_instance_private_nic" "this" {
  private_network_id = var.private_network_id
  server_id          = var.server_id
  zone               = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = scaleway_instance_private_nic.this.id
}

output "mac_address" {
  description = "returns a string"
  value       = scaleway_instance_private_nic.this.mac_address
}

output "zone" {
  description = "returns a string"
  value       = scaleway_instance_private_nic.this.zone
}

output "this" {
  value = scaleway_instance_private_nic.this
}
```

[top](#index)