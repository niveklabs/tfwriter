# packet_device_bgp_neighbors

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
module "packet_device_bgp_neighbors" {
  source = "./modules/packet/d/packet_device_bgp_neighbors"

  # device_id - (required) is a type of string
  device_id = null
}
```

[top](#index)

### Variables

```terraform
variable "device_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "packet_device_bgp_neighbors" "this" {
  device_id = var.device_id
}
```

[top](#index)

### Outputs

```terraform
output "bgp_neighbors" {
  description = "returns a list of object"
  value       = data.packet_device_bgp_neighbors.this.bgp_neighbors
}

output "id" {
  description = "returns a string"
  value       = data.packet_device_bgp_neighbors.this.id
}

output "this" {
  value = packet_device_bgp_neighbors.this
}
```

[top](#index)