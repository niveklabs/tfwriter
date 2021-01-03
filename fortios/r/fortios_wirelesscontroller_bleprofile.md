# fortios_wirelesscontroller_bleprofile

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
    fortios = ">= 1.6.18"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "fortios_wirelesscontroller_bleprofile" {
  source = "./modules/fortios/r/fortios_wirelesscontroller_bleprofile"

  # advertising - (optional) is a type of string
  advertising = null
  # beacon_interval - (optional) is a type of number
  beacon_interval = null
  # ble_scanning - (optional) is a type of string
  ble_scanning = null
  # comment - (optional) is a type of string
  comment = null
  # eddystone_instance - (optional) is a type of string
  eddystone_instance = null
  # eddystone_namespace - (optional) is a type of string
  eddystone_namespace = null
  # eddystone_url - (optional) is a type of string
  eddystone_url = null
  # eddystone_url_encode_hex - (optional) is a type of string
  eddystone_url_encode_hex = null
  # ibeacon_uuid - (optional) is a type of string
  ibeacon_uuid = null
  # major_id - (optional) is a type of number
  major_id = null
  # minor_id - (optional) is a type of number
  minor_id = null
  # name - (optional) is a type of string
  name = null
  # txpower - (optional) is a type of string
  txpower = null
}
```

[top](#index)

### Variables

```terraform
variable "advertising" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "beacon_interval" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "ble_scanning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "comment" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eddystone_instance" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eddystone_namespace" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eddystone_url" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "eddystone_url_encode_hex" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ibeacon_uuid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "major_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "minor_id" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "txpower" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_wirelesscontroller_bleprofile" "this" {
  advertising              = var.advertising
  beacon_interval          = var.beacon_interval
  ble_scanning             = var.ble_scanning
  comment                  = var.comment
  eddystone_instance       = var.eddystone_instance
  eddystone_namespace      = var.eddystone_namespace
  eddystone_url            = var.eddystone_url
  eddystone_url_encode_hex = var.eddystone_url_encode_hex
  ibeacon_uuid             = var.ibeacon_uuid
  major_id                 = var.major_id
  minor_id                 = var.minor_id
  name                     = var.name
  txpower                  = var.txpower
}
```

[top](#index)

### Outputs

```terraform
output "advertising" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bleprofile.this.advertising
}

output "beacon_interval" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_bleprofile.this.beacon_interval
}

output "ble_scanning" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bleprofile.this.ble_scanning
}

output "comment" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bleprofile.this.comment
}

output "eddystone_instance" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bleprofile.this.eddystone_instance
}

output "eddystone_namespace" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bleprofile.this.eddystone_namespace
}

output "eddystone_url" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bleprofile.this.eddystone_url
}

output "eddystone_url_encode_hex" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bleprofile.this.eddystone_url_encode_hex
}

output "ibeacon_uuid" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bleprofile.this.ibeacon_uuid
}

output "id" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bleprofile.this.id
}

output "major_id" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_bleprofile.this.major_id
}

output "minor_id" {
  description = "returns a number"
  value       = fortios_wirelesscontroller_bleprofile.this.minor_id
}

output "name" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bleprofile.this.name
}

output "txpower" {
  description = "returns a string"
  value       = fortios_wirelesscontroller_bleprofile.this.txpower
}

output "this" {
  value = fortios_wirelesscontroller_bleprofile.this
}
```

[top](#index)