# fortios_system_clustersync

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
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
module "fortios_system_clustersync" {
  source = "./modules/fortios/d/fortios_system_clustersync"

  # sync_id - (required) is a type of number
  sync_id = null
}
```

[top](#index)

### Variables

```terraform
variable "sync_id" {
  description = "(required)"
  type        = number
}
```

[top](#index)

### Datasource

```terraform
data "fortios_system_clustersync" "this" {
  sync_id = var.sync_id
}
```

[top](#index)

### Outputs

```terraform
output "down_intfs_before_sess_sync" {
  description = "returns a list of object"
  value       = data.fortios_system_clustersync.this.down_intfs_before_sess_sync
}

output "hb_interval" {
  description = "returns a number"
  value       = data.fortios_system_clustersync.this.hb_interval
}

output "hb_lost_threshold" {
  description = "returns a number"
  value       = data.fortios_system_clustersync.this.hb_lost_threshold
}

output "id" {
  description = "returns a string"
  value       = data.fortios_system_clustersync.this.id
}

output "ipsec_tunnel_sync" {
  description = "returns a string"
  value       = data.fortios_system_clustersync.this.ipsec_tunnel_sync
}

output "peerip" {
  description = "returns a string"
  value       = data.fortios_system_clustersync.this.peerip
}

output "peervd" {
  description = "returns a string"
  value       = data.fortios_system_clustersync.this.peervd
}

output "session_sync_filter" {
  description = "returns a list of object"
  value       = data.fortios_system_clustersync.this.session_sync_filter
}

output "slave_add_ike_routes" {
  description = "returns a string"
  value       = data.fortios_system_clustersync.this.slave_add_ike_routes
}

output "syncvd" {
  description = "returns a list of object"
  value       = data.fortios_system_clustersync.this.syncvd
}

output "this" {
  value = fortios_system_clustersync.this
}
```

[top](#index)