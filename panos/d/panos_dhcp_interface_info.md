# panos_dhcp_interface_info

[back](../panos.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    panos = ">= 1.6.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "panos_dhcp_interface_info" {
  source = "./modules/panos/d/panos_dhcp_interface_info"

  # interface - (required) is a type of string
  interface = null
}
```

[top](#index)

### Variables

```terraform
variable "interface" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Datasource

```terraform
data "panos_dhcp_interface_info" "this" {
  interface = var.interface
}
```

[top](#index)

### Outputs

```terraform
output "dns_suffix" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.dns_suffix
}

output "gateway" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.gateway
}

output "id" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.id
}

output "ip" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.ip
}

output "pop3_server" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.pop3_server
}

output "primary_dns" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.primary_dns
}

output "primary_nis" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.primary_nis
}

output "primary_ntp" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.primary_ntp
}

output "primary_wins" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.primary_wins
}

output "secondary_dns" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.secondary_dns
}

output "secondary_nis" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.secondary_nis
}

output "secondary_ntp" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.secondary_ntp
}

output "secondary_wins" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.secondary_wins
}

output "server" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.server
}

output "server_id" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.server_id
}

output "smtp_server" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.smtp_server
}

output "state" {
  description = "returns a string"
  value       = data.panos_dhcp_interface_info.this.state
}

output "this" {
  value = panos_dhcp_interface_info.this
}
```

[top](#index)