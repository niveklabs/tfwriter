# ovh_dedicated_server

[back](../ovh.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    ovh = ">= 0.10.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_dedicated_server" {
  source = "./modules/ovh/d/ovh_dedicated_server"

  # service_name - (required) is a type of string
  service_name = null
}
```

[top](#index)

### Variables

```terraform
variable "service_name" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "ovh_dedicated_server" "this" {
  service_name = var.service_name
}
```

[top](#index)

### Outputs

```terraform
output "boot_id" {
  description = "returns a number"
  value       = data.ovh_dedicated_server.this.boot_id
}

output "commercial_range" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.commercial_range
}

output "datacenter" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.datacenter
}

output "enabled_public_vnis" {
  description = "returns a list of string"
  value       = data.ovh_dedicated_server.this.enabled_public_vnis
}

output "enabled_vrack_aggregation_vnis" {
  description = "returns a list of string"
  value       = data.ovh_dedicated_server.this.enabled_vrack_aggregation_vnis
}

output "enabled_vrack_vnis" {
  description = "returns a list of string"
  value       = data.ovh_dedicated_server.this.enabled_vrack_vnis
}

output "id" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.id
}

output "ip" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.ip
}

output "ips" {
  description = "returns a list of string"
  value       = data.ovh_dedicated_server.this.ips
}

output "link_speed" {
  description = "returns a number"
  value       = data.ovh_dedicated_server.this.link_speed
}

output "monitoring" {
  description = "returns a bool"
  value       = data.ovh_dedicated_server.this.monitoring
}

output "name" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.name
}

output "os" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.os
}

output "professional_use" {
  description = "returns a bool"
  value       = data.ovh_dedicated_server.this.professional_use
}

output "rack" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.rack
}

output "rescue_mail" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.rescue_mail
}

output "reverse" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.reverse
}

output "root_device" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.root_device
}

output "server_id" {
  description = "returns a number"
  value       = data.ovh_dedicated_server.this.server_id
}

output "state" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.state
}

output "support_level" {
  description = "returns a string"
  value       = data.ovh_dedicated_server.this.support_level
}

output "vnis" {
  description = "returns a list of object"
  value       = data.ovh_dedicated_server.this.vnis
}

output "this" {
  value = ovh_dedicated_server.this
}
```

[top](#index)