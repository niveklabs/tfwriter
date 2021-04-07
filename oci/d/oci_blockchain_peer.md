# oci_blockchain_peer

[back](../oci.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
  source = "./modules/oci/d/oci_blockchain_peer"

  # blockchain_platform_id - (required) is a type of string
  blockchain_platform_id = null
  # peer_id - (required) is a type of string
  peer_id = null
}
```

[top](#index)

### Variables

```terraform
variable "blockchain_platform_id" {
  description = "(required)"
  type        = string
}

variable "peer_id" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "oci_blockchain_peer" "this" {
  # blockchain_platform_id - (required) is a type of string
  blockchain_platform_id = var.blockchain_platform_id
  # peer_id - (required) is a type of string
  peer_id = var.peer_id
}
```

[top](#index)

### Outputs

```terraform
output "ad" {
  description = "returns a string"
  value       = data.oci_blockchain_peer.this.ad
}

output "alias" {
  description = "returns a string"
  value       = data.oci_blockchain_peer.this.alias
}

output "host" {
  description = "returns a string"
  value       = data.oci_blockchain_peer.this.host
}

output "id" {
  description = "returns a string"
  value       = data.oci_blockchain_peer.this.id
}

output "ocpu_allocation_param" {
  description = "returns a list of object"
  value       = data.oci_blockchain_peer.this.ocpu_allocation_param
}

output "peer_key" {
  description = "returns a string"
  value       = data.oci_blockchain_peer.this.peer_key
}

output "role" {
  description = "returns a string"
  value       = data.oci_blockchain_peer.this.role
}

output "state" {
  description = "returns a string"
  value       = data.oci_blockchain_peer.this.state
}

output "this" {
  value = oci_blockchain_peer.this
}
```

[top](#index)