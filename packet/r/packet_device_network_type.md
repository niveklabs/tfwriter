# packet_device_network_type

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
module "packet_device_network_type" {
  source = "./modules/packet/r/packet_device_network_type"

  # device_id - (required) is a type of string
  device_id = null
  # type - (required) is a type of string
  type = null
}
```

[top](#index)

### Variables

```terraform
variable "device_id" {
  description = "(required)"
  type        = string
}

variable "type" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "packet_device_network_type" "this" {
  device_id = var.device_id
  type      = var.type
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = packet_device_network_type.this.id
}

output "this" {
  value = packet_device_network_type.this
}
```

[top](#index)