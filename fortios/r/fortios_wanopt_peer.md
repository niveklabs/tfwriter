# fortios_wanopt_peer

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    fortios = ">= 1.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wanopt_peer" {
  source = "./modules/fortios/r/fortios_wanopt_peer"

  # ip - (optional) is a type of string
  ip = null
  # peer_host_id - (optional) is a type of string
  peer_host_id = null
}
```

[top](#index)

### Variables

```terraform
variable "ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer_host_id" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wanopt_peer" "this" {
  ip           = var.ip
  peer_host_id = var.peer_host_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_wanopt_peer.this.id
}

output "ip" {
  description = "returns a string"
  value       = fortios_wanopt_peer.this.ip
}

output "peer_host_id" {
  description = "returns a string"
  value       = fortios_wanopt_peer.this.peer_host_id
}

output "this" {
  value = fortios_wanopt_peer.this
}
```

[top](#index)