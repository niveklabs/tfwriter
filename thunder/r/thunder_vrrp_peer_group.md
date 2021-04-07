# thunder_vrrp_peer_group

[back](../thunder.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    thunder = ">= 0.4.16"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "thunder_vrrp_peer_group" {
  source = "./modules/thunder/r/thunder_vrrp_peer_group"

  # uuid - (optional) is a type of string
  uuid = null

  peer = [{
    ip_peer_address_cfg = [{
      ip_peer_address = null
    }]
    ipv6_peer_address_cfg = [{
      ipv6_peer_address = null
    }]
  }]
}
```

[top](#index)

### Variables

```terraform
variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "peer" {
  description = "nested block: NestingList, min items: 0, max items: 1"
  type = set(object(
    {
      ip_peer_address_cfg = list(object(
        {
          ip_peer_address = string
        }
      ))
      ipv6_peer_address_cfg = list(object(
        {
          ipv6_peer_address = string
        }
      ))
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "thunder_vrrp_peer_group" "this" {
  # uuid - (optional) is a type of string
  uuid = var.uuid

  dynamic "peer" {
    for_each = var.peer
    content {

      dynamic "ip_peer_address_cfg" {
        for_each = peer.value.ip_peer_address_cfg
        content {
          # ip_peer_address - (optional) is a type of string
          ip_peer_address = ip_peer_address_cfg.value["ip_peer_address"]
        }
      }

      dynamic "ipv6_peer_address_cfg" {
        for_each = peer.value.ipv6_peer_address_cfg
        content {
          # ipv6_peer_address - (optional) is a type of string
          ipv6_peer_address = ipv6_peer_address_cfg.value["ipv6_peer_address"]
        }
      }

    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = thunder_vrrp_peer_group.this.id
}

output "this" {
  value = thunder_vrrp_peer_group.this
}
```

[top](#index)