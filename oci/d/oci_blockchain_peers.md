# oci_blockchain_peers

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
module "oci_blockchain_peers" {
  source = "./modules/oci/d/oci_blockchain_peers"

  # blockchain_platform_id - (required) is a type of string
  blockchain_platform_id = null
  # display_name - (optional) is a type of string
  display_name = null

  filter = [{
    name   = null
    regex  = null
    values = []
  }]
}
```

[top](#index)

### Variables

```terraform
variable "blockchain_platform_id" {
  description = "(required)"
  type        = string
}

variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "filter" {
  description = "nested block: NestingSet, min items: 0, max items: 0"
  type = set(object(
    {
      name   = string
      regex  = bool
      values = list(string)
    }
  ))
  default = []
}
```

[top](#index)

### Datasource

```terraform
data "oci_blockchain_peers" "this" {
  blockchain_platform_id = var.blockchain_platform_id
  display_name           = var.display_name

  dynamic "filter" {
    for_each = var.filter
    content {
      name   = filter.value["name"]
      regex  = filter.value["regex"]
      values = filter.value["values"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = data.oci_blockchain_peers.this.id
}

output "peer_collection" {
  description = "returns a list of object"
  value       = data.oci_blockchain_peers.this.peer_collection
}

output "this" {
  value = oci_blockchain_peers.this
}
```

[top](#index)