# fortios_wirelesscontrollerhotspot20_h2qpconncapability

[back](../fortios.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
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
module "fortios_wirelesscontrollerhotspot20_h2qpconncapability" {
  source = "./modules/fortios/r/fortios_wirelesscontrollerhotspot20_h2qpconncapability"

  # esp_port - (optional) is a type of string
  esp_port = null
  # ftp_port - (optional) is a type of string
  ftp_port = null
  # http_port - (optional) is a type of string
  http_port = null
  # icmp_port - (optional) is a type of string
  icmp_port = null
  # ikev2_port - (optional) is a type of string
  ikev2_port = null
  # ikev2_xx_port - (optional) is a type of string
  ikev2_xx_port = null
  # name - (optional) is a type of string
  name = null
  # pptp_vpn_port - (optional) is a type of string
  pptp_vpn_port = null
  # ssh_port - (optional) is a type of string
  ssh_port = null
  # tls_port - (optional) is a type of string
  tls_port = null
  # voip_tcp_port - (optional) is a type of string
  voip_tcp_port = null
  # voip_udp_port - (optional) is a type of string
  voip_udp_port = null
}
```

[top](#index)

### Variables

```terraform
variable "esp_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ftp_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "http_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "icmp_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ikev2_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ikev2_xx_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pptp_vpn_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tls_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "voip_tcp_port" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "voip_udp_port" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontrollerhotspot20_h2qpconncapability" "this" {
  # esp_port - (optional) is a type of string
  esp_port = var.esp_port
  # ftp_port - (optional) is a type of string
  ftp_port = var.ftp_port
  # http_port - (optional) is a type of string
  http_port = var.http_port
  # icmp_port - (optional) is a type of string
  icmp_port = var.icmp_port
  # ikev2_port - (optional) is a type of string
  ikev2_port = var.ikev2_port
  # ikev2_xx_port - (optional) is a type of string
  ikev2_xx_port = var.ikev2_xx_port
  # name - (optional) is a type of string
  name = var.name
  # pptp_vpn_port - (optional) is a type of string
  pptp_vpn_port = var.pptp_vpn_port
  # ssh_port - (optional) is a type of string
  ssh_port = var.ssh_port
  # tls_port - (optional) is a type of string
  tls_port = var.tls_port
  # voip_tcp_port - (optional) is a type of string
  voip_tcp_port = var.voip_tcp_port
  # voip_udp_port - (optional) is a type of string
  voip_udp_port = var.voip_udp_port
}
```

[top](#index)

### Outputs

```terraform
output "esp_port" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.esp_port
}

output "ftp_port" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.ftp_port
}

output "http_port" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.http_port
}

output "icmp_port" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.icmp_port
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.id
}

output "ikev2_port" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.ikev2_port
}

output "ikev2_xx_port" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.ikev2_xx_port
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.name
}

output "pptp_vpn_port" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.pptp_vpn_port
}

output "ssh_port" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.ssh_port
}

output "tls_port" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.tls_port
}

output "voip_tcp_port" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.voip_tcp_port
}

output "voip_udp_port" {
  description = "returns a string"
  value       = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this.voip_udp_port
}

output "this" {
  value = fortios_wirelesscontrollerhotspot20_h2qpconncapability.this
}
```

[top](#index)