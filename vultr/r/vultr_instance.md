# vultr_instance

[back](../vultr.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vultr = ">= 2.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vultr_instance" {
  source = "./modules/vultr/r/vultr_instance"

  # activation_email - (optional) is a type of bool
  activation_email = null
  # app_id - (optional) is a type of number
  app_id = null
  # backups - (optional) is a type of string
  backups = null
  # ddos_protection - (optional) is a type of bool
  ddos_protection = null
  # enable_ipv6 - (optional) is a type of bool
  enable_ipv6 = null
  # enable_private_network - (optional) is a type of bool
  enable_private_network = null
  # firewall_group_id - (optional) is a type of string
  firewall_group_id = null
  # hostname - (optional) is a type of string
  hostname = null
  # iso_id - (optional) is a type of string
  iso_id = null
  # label - (optional) is a type of string
  label = null
  # os_id - (optional) is a type of number
  os_id = null
  # plan - (required) is a type of string
  plan = null
  # private_network_ids - (optional) is a type of list of string
  private_network_ids = []
  # region - (required) is a type of string
  region = null
  # reserved_ip_id - (optional) is a type of string
  reserved_ip_id = null
  # script_id - (optional) is a type of string
  script_id = null
  # snapshot_id - (optional) is a type of string
  snapshot_id = null
  # ssh_key_ids - (optional) is a type of list of string
  ssh_key_ids = []
  # tag - (optional) is a type of string
  tag = null
  # user_data - (optional) is a type of string
  user_data = null
}
```

[top](#index)

### Variables

```terraform
variable "activation_email" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "app_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "backups" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ddos_protection" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_ipv6" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "enable_private_network" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "firewall_group_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hostname" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iso_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "label" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "os_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "plan" {
  description = "(required)"
  type        = string
}

variable "private_network_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "region" {
  description = "(required)"
  type        = string
}

variable "reserved_ip_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "script_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "snapshot_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssh_key_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "tag" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_data" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vultr_instance" "this" {
  # activation_email - (optional) is a type of bool
  activation_email = var.activation_email
  # app_id - (optional) is a type of number
  app_id = var.app_id
  # backups - (optional) is a type of string
  backups = var.backups
  # ddos_protection - (optional) is a type of bool
  ddos_protection = var.ddos_protection
  # enable_ipv6 - (optional) is a type of bool
  enable_ipv6 = var.enable_ipv6
  # enable_private_network - (optional) is a type of bool
  enable_private_network = var.enable_private_network
  # firewall_group_id - (optional) is a type of string
  firewall_group_id = var.firewall_group_id
  # hostname - (optional) is a type of string
  hostname = var.hostname
  # iso_id - (optional) is a type of string
  iso_id = var.iso_id
  # label - (optional) is a type of string
  label = var.label
  # os_id - (optional) is a type of number
  os_id = var.os_id
  # plan - (required) is a type of string
  plan = var.plan
  # private_network_ids - (optional) is a type of list of string
  private_network_ids = var.private_network_ids
  # region - (required) is a type of string
  region = var.region
  # reserved_ip_id - (optional) is a type of string
  reserved_ip_id = var.reserved_ip_id
  # script_id - (optional) is a type of string
  script_id = var.script_id
  # snapshot_id - (optional) is a type of string
  snapshot_id = var.snapshot_id
  # ssh_key_ids - (optional) is a type of list of string
  ssh_key_ids = var.ssh_key_ids
  # tag - (optional) is a type of string
  tag = var.tag
  # user_data - (optional) is a type of string
  user_data = var.user_data
}
```

[top](#index)

### Outputs

```terraform
output "allowed_bandwidth" {
  description = "returns a number"
  value       = vultr_instance.this.allowed_bandwidth
}

output "app_id" {
  description = "returns a number"
  value       = vultr_instance.this.app_id
}

output "date_created" {
  description = "returns a string"
  value       = vultr_instance.this.date_created
}

output "default_password" {
  description = "returns a string"
  value       = vultr_instance.this.default_password
  sensitive   = true
}

output "disk" {
  description = "returns a number"
  value       = vultr_instance.this.disk
}

output "features" {
  description = "returns a list of string"
  value       = vultr_instance.this.features
}

output "firewall_group_id" {
  description = "returns a string"
  value       = vultr_instance.this.firewall_group_id
}

output "gateway_v4" {
  description = "returns a string"
  value       = vultr_instance.this.gateway_v4
}

output "hostname" {
  description = "returns a string"
  value       = vultr_instance.this.hostname
}

output "id" {
  description = "returns a string"
  value       = vultr_instance.this.id
}

output "internal_ip" {
  description = "returns a string"
  value       = vultr_instance.this.internal_ip
}

output "kvm" {
  description = "returns a string"
  value       = vultr_instance.this.kvm
}

output "label" {
  description = "returns a string"
  value       = vultr_instance.this.label
}

output "main_ip" {
  description = "returns a string"
  value       = vultr_instance.this.main_ip
}

output "netmask_v4" {
  description = "returns a string"
  value       = vultr_instance.this.netmask_v4
}

output "os" {
  description = "returns a string"
  value       = vultr_instance.this.os
}

output "os_id" {
  description = "returns a number"
  value       = vultr_instance.this.os_id
}

output "power_status" {
  description = "returns a string"
  value       = vultr_instance.this.power_status
}

output "ram" {
  description = "returns a number"
  value       = vultr_instance.this.ram
}

output "reserved_ip_id" {
  description = "returns a string"
  value       = vultr_instance.this.reserved_ip_id
}

output "script_id" {
  description = "returns a string"
  value       = vultr_instance.this.script_id
}

output "server_status" {
  description = "returns a string"
  value       = vultr_instance.this.server_status
}

output "snapshot_id" {
  description = "returns a string"
  value       = vultr_instance.this.snapshot_id
}

output "status" {
  description = "returns a string"
  value       = vultr_instance.this.status
}

output "tag" {
  description = "returns a string"
  value       = vultr_instance.this.tag
}

output "user_data" {
  description = "returns a string"
  value       = vultr_instance.this.user_data
}

output "v6_main_ip" {
  description = "returns a string"
  value       = vultr_instance.this.v6_main_ip
}

output "v6_network" {
  description = "returns a string"
  value       = vultr_instance.this.v6_network
}

output "v6_network_size" {
  description = "returns a number"
  value       = vultr_instance.this.v6_network_size
}

output "vcpu_count" {
  description = "returns a number"
  value       = vultr_instance.this.vcpu_count
}

output "this" {
  value = vultr_instance.this
}
```

[top](#index)