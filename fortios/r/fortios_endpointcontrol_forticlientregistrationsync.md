# fortios_endpointcontrol_forticlientregistrationsync

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
module "fortios_endpointcontrol_forticlientregistrationsync" {
  source = "./modules/fortios/r/fortios_endpointcontrol_forticlientregistrationsync"

  # peer_ip - (required) is a type of string
  peer_ip = null
  # peer_name - (optional) is a type of string
  peer_name = null
}
```

[top](#index)

### Variables

```terraform
variable "peer_ip" {
  description = "(required)"
  type        = string
}

variable "peer_name" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_endpointcontrol_forticlientregistrationsync" "this" {
  # peer_ip - (required) is a type of string
  peer_ip = var.peer_ip
  # peer_name - (optional) is a type of string
  peer_name = var.peer_name
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = fortios_endpointcontrol_forticlientregistrationsync.this.id
}

output "peer_name" {
  description = "returns a string"
  value       = fortios_endpointcontrol_forticlientregistrationsync.this.peer_name
}

output "this" {
  value = fortios_endpointcontrol_forticlientregistrationsync.this
}
```

[top](#index)