# ovh_iploadbalancing

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
    ovh = ">= 0.11.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "ovh_iploadbalancing" {
  source = "./modules/ovh/d/ovh_iploadbalancing"

  # display_name - (optional) is a type of string
  display_name = null
  # ip_loadbalancing - (optional) is a type of string
  ip_loadbalancing = null
  # ipv4 - (optional) is a type of string
  ipv4 = null
  # ipv6 - (optional) is a type of string
  ipv6 = null
  # offer - (optional) is a type of string
  offer = null
  # service_name - (optional) is a type of string
  service_name = null
  # ssl_configuration - (optional) is a type of string
  ssl_configuration = null
  # state - (optional) is a type of string
  state = null
  # vrack_eligibility - (optional) is a type of bool
  vrack_eligibility = null
  # vrack_name - (optional) is a type of string
  vrack_name = null
  # zone - (optional) is a type of set of string
  zone = []
}
```

[top](#index)

### Variables

```terraform
variable "display_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ip_loadbalancing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv4" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ipv6" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "offer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "service_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_configuration" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "state" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "vrack_eligibility" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "vrack_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "zone" {
  description = "(optional)"
  type        = set(string)
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "ovh_iploadbalancing" "this" {
  display_name      = var.display_name
  ip_loadbalancing  = var.ip_loadbalancing
  ipv4              = var.ipv4
  ipv6              = var.ipv6
  offer             = var.offer
  service_name      = var.service_name
  ssl_configuration = var.ssl_configuration
  state             = var.state
  vrack_eligibility = var.vrack_eligibility
  vrack_name        = var.vrack_name
  zone              = var.zone
}
```

[top](#index)

### Outputs

```terraform
output "display_name" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing.this.display_name
}

output "id" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing.this.id
}

output "ip_loadbalancing" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing.this.ip_loadbalancing
}

output "ipv4" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing.this.ipv4
}

output "ipv6" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing.this.ipv6
}

output "metrics_token" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing.this.metrics_token
  sensitive   = true
}

output "offer" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing.this.offer
}

output "orderable_zone" {
  description = "returns a set of object"
  value       = data.ovh_iploadbalancing.this.orderable_zone
}

output "service_name" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing.this.service_name
}

output "ssl_configuration" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing.this.ssl_configuration
}

output "state" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing.this.state
}

output "vrack_eligibility" {
  description = "returns a bool"
  value       = data.ovh_iploadbalancing.this.vrack_eligibility
}

output "vrack_name" {
  description = "returns a string"
  value       = data.ovh_iploadbalancing.this.vrack_name
}

output "zone" {
  description = "returns a set of string"
  value       = data.ovh_iploadbalancing.this.zone
}

output "this" {
  value = ovh_iploadbalancing.this
}
```

[top](#index)