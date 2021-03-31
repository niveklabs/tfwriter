# checkpoint_management_simple_gateway

[back](../checkpoint.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    checkpoint = ">= 1.4.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "checkpoint_management_simple_gateway" {
  source = "./modules/checkpoint/d/checkpoint_management_simple_gateway"

  # name - (optional) is a type of string
  name = null
  # uid - (optional) is a type of string
  uid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional) - Object name. Should be unique in the domain."
  type        = string
  default     = null
}

variable "uid" {
  description = "(optional) - Object unique identifier."
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "checkpoint_management_simple_gateway" "this" {
  name = var.name
  uid  = var.uid
}
```

[top](#index)

### Outputs

```terraform
output "anti_bot" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.anti_bot
}

output "anti_virus" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.anti_virus
}

output "application_control" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.application_control
}

output "color" {
  description = "returns a string"
  value       = data.checkpoint_management_simple_gateway.this.color
}

output "comments" {
  description = "returns a string"
  value       = data.checkpoint_management_simple_gateway.this.comments
}

output "content_awareness" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.content_awareness
}

output "dynamic_ip" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.dynamic_ip
}

output "firewall" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.firewall
}

output "firewall_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_simple_gateway.this.firewall_settings
}

output "hardware" {
  description = "returns a string"
  value       = data.checkpoint_management_simple_gateway.this.hardware
}

output "icap_server" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.icap_server
}

output "id" {
  description = "returns a string"
  value       = data.checkpoint_management_simple_gateway.this.id
}

output "interfaces" {
  description = "returns a list of object"
  value       = data.checkpoint_management_simple_gateway.this.interfaces
}

output "ips" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.ips
}

output "ipv4_address" {
  description = "returns a string"
  value       = data.checkpoint_management_simple_gateway.this.ipv4_address
}

output "ipv6_address" {
  description = "returns a string"
  value       = data.checkpoint_management_simple_gateway.this.ipv6_address
}

output "logs_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_simple_gateway.this.logs_settings
}

output "os_name" {
  description = "returns a string"
  value       = data.checkpoint_management_simple_gateway.this.os_name
}

output "save_logs_locally" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.save_logs_locally
}

output "send_alerts_to_server" {
  description = "returns a set of string"
  value       = data.checkpoint_management_simple_gateway.this.send_alerts_to_server
}

output "send_logs_to_backup_server" {
  description = "returns a set of string"
  value       = data.checkpoint_management_simple_gateway.this.send_logs_to_backup_server
}

output "send_logs_to_server" {
  description = "returns a set of string"
  value       = data.checkpoint_management_simple_gateway.this.send_logs_to_server
}

output "sic_name" {
  description = "returns a string"
  value       = data.checkpoint_management_simple_gateway.this.sic_name
}

output "sic_state" {
  description = "returns a string"
  value       = data.checkpoint_management_simple_gateway.this.sic_state
}

output "tags" {
  description = "returns a set of string"
  value       = data.checkpoint_management_simple_gateway.this.tags
}

output "threat_emulation" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.threat_emulation
}

output "threat_extraction" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.threat_extraction
}

output "url_filtering" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.url_filtering
}

output "version" {
  description = "returns a string"
  value       = data.checkpoint_management_simple_gateway.this.version
}

output "vpn" {
  description = "returns a bool"
  value       = data.checkpoint_management_simple_gateway.this.vpn
}

output "vpn_settings" {
  description = "returns a map of string"
  value       = data.checkpoint_management_simple_gateway.this.vpn_settings
}

output "this" {
  value = checkpoint_management_simple_gateway.this
}
```

[top](#index)