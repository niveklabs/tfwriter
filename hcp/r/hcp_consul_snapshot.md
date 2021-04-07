# hcp_consul_snapshot

[back](../hcp.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    hcp = ">= 0.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "hcp_consul_snapshot" {
  source = "./modules/hcp/r/hcp_consul_snapshot"

  # cluster_id - (required) is a type of string
  cluster_id = null
  # snapshot_name - (required) is a type of string
  snapshot_name = null

  timeouts = [{
    create  = null
    default = null
    delete  = null
    update  = null
  }]
}
```

[top](#index)

### Variables

```terraform
variable "cluster_id" {
  description = "(required) - The ID of the HCP Consul cluster."
  type        = string
}

variable "snapshot_name" {
  description = "(required) - The name of the snapshot."
  type        = string
}

variable "timeouts" {
  description = "nested block: NestingSingle, min items: 0, max items: 0"
  type = set(object(
    {
      create  = string
      default = string
      delete  = string
      update  = string
    }
  ))
  default = []
}
```

[top](#index)

### Resource

```terraform
resource "hcp_consul_snapshot" "this" {
  cluster_id    = var.cluster_id
  snapshot_name = var.snapshot_name

  dynamic "timeouts" {
    for_each = var.timeouts
    content {
      create  = timeouts.value["create"]
      default = timeouts.value["default"]
      delete  = timeouts.value["delete"]
      update  = timeouts.value["update"]
    }
  }

}
```

[top](#index)

### Outputs

```terraform
output "consul_version" {
  description = "returns a string"
  value       = hcp_consul_snapshot.this.consul_version
}

output "id" {
  description = "returns a string"
  value       = hcp_consul_snapshot.this.id
}

output "organization_id" {
  description = "returns a string"
  value       = hcp_consul_snapshot.this.organization_id
}

output "project_id" {
  description = "returns a string"
  value       = hcp_consul_snapshot.this.project_id
}

output "restored_at" {
  description = "returns a string"
  value       = hcp_consul_snapshot.this.restored_at
}

output "size" {
  description = "returns a number"
  value       = hcp_consul_snapshot.this.size
}

output "snapshot_id" {
  description = "returns a string"
  value       = hcp_consul_snapshot.this.snapshot_id
}

output "this" {
  value = hcp_consul_snapshot.this
}
```

[top](#index)