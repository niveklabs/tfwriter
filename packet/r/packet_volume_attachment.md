# packet_volume_attachment

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
module "packet_volume_attachment" {
  source = "./modules/packet/r/packet_volume_attachment"

  # device_id - (required) is a type of string
  device_id = null
  # volume_id - (required) is a type of string
  volume_id = null
}
```

[top](#index)

### Variables

```terraform
variable "device_id" {
  description = "(required)"
  type        = string
}

variable "volume_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "packet_volume_attachment" "this" {
  device_id = var.device_id
  volume_id = var.volume_id
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = packet_volume_attachment.this.id
}

output "this" {
  value = packet_volume_attachment.this
}
```

[top](#index)