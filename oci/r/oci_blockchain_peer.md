# oci_blockchain_peer

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    oci = ">= 4.21.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "oci_blockchain_peer" {
  source = "./modules/oci/r/oci_blockchain_peer"

  # ad - (required) is a type of string
  ad = null
  # alias - (optional) is a type of string
  alias = null
  # blockchain_platform_id - (required) is a type of string
  blockchain_platform_id = null
  # role - (required) is a type of string
  role = null

  ocpu_allocation_param = [{
    ocpu_allocation_number = null
  }]

  timeouts = [{
    create = null
    delete = null
    update = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "ad" {
  description = "(required)"
  type        = string
}

variable "alias" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "blockchain_platform_id" {
  description = "(required)"
  type        = string
}

variable "role" {
  description = "(required)"
  type        = string
}

variable "ocpu_allocation_param" {
  description = "nested block: NestingList, min items: 1, max items: 1"
  type = set(object(
    {
      ocpu_allocation_number = number
    }
  ))
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create = string
      delete = string
      update = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "oci_blockchain_peer" "this" {
  ad                     = var.ad
  alias                  = var.alias
  blockchain_platform_id = var.blockchain_platform_id
  role                   = var.role

  dynamic "ocpu_allocation_param" {
    for_each = var.ocpu_allocation_param
    content {
      ocpu_allocation_number = ocpu_allocation_param.value["ocpu_allocation_number"]
    }
  }

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create = timeouts.value["create"]
      delete = timeouts.value["delete"]
      update = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "alias" {
  description = "returns a string"
  value       = oci_blockchain_peer.this.alias
}

output "host" {
  description = "returns a string"
  value       = oci_blockchain_peer.this.host
}

output "id" {
  description = "returns a string"
  value       = oci_blockchain_peer.this.id
}

output "peer_key" {
  description = "returns a string"
  value       = oci_blockchain_peer.this.peer_key
}

output "state" {
  description = "returns a string"
  value       = oci_blockchain_peer.this.state
}

output "this" {
  value = oci_blockchain_peer.this
}
```

[top](#index)