# scaleway_instance_server

[back](../scaleway.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    scaleway = ">= 2.0.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "scaleway_instance_server" {
  source = "./modules/scaleway/d/scaleway_instance_server"

  # name - (optional) is a type of string
  name = null
  # server_id - (optional) is a type of string
  server_id = null
  # zone - (optional) is a type of string
  zone = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - The name of the server"
  type        = string
  default     = null
}

variable "server_id" {
  description = "(optional) - The ID of the server"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional) - The zone you want to attach the resource to"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "scaleway_instance_server" "this" {
  name      = var.name
  server_id = var.server_id
  zone      = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "additional_volume_ids" {
  description = "returns a list of string"
  value       = data.scaleway_instance_server.this.additional_volume_ids
}

output "boot_type" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.boot_type
}

output "bootscript_id" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.bootscript_id
}

output "cloud_init" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.cloud_init
}

output "enable_dynamic_ip" {
  description = "returns a bool"
  value       = data.scaleway_instance_server.this.enable_dynamic_ip
}

output "enable_ipv6" {
  description = "returns a bool"
  value       = data.scaleway_instance_server.this.enable_ipv6
}

output "id" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.id
}

output "image" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.image
}

output "ip_id" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.ip_id
}

output "ipv6_address" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.ipv6_address
}

output "ipv6_gateway" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.ipv6_gateway
}

output "ipv6_prefix_length" {
  description = "returns a number"
  value       = data.scaleway_instance_server.this.ipv6_prefix_length
}

output "organization_id" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.organization_id
}

output "placement_group_id" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.placement_group_id
}

output "placement_group_policy_respected" {
  description = "returns a bool"
  value       = data.scaleway_instance_server.this.placement_group_policy_respected
}

output "private_ip" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.private_ip
}

output "project_id" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.project_id
}

output "public_ip" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.public_ip
}

output "root_volume" {
  description = "returns a list of object"
  value       = data.scaleway_instance_server.this.root_volume
}

output "security_group_id" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.security_group_id
}

output "state" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.state
}

output "tags" {
  description = "returns a list of string"
  value       = data.scaleway_instance_server.this.tags
}

output "type" {
  description = "returns a string"
  value       = data.scaleway_instance_server.this.type
}

output "user_data" {
  description = "returns a map of string"
  value       = data.scaleway_instance_server.this.user_data
}

output "this" {
  value = scaleway_instance_server.this
}
```

[top](#index)