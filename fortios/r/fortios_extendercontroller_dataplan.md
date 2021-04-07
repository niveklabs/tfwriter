# fortios_extendercontroller_dataplan

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
module "fortios_extendercontroller_dataplan" {
  source = "./modules/fortios/r/fortios_extendercontroller_dataplan"

  # apn - (optional) is a type of string
  apn = null
  # auth_type - (optional) is a type of string
  auth_type = null
  # billing_date - (optional) is a type of number
  billing_date = null
  # capacity - (optional) is a type of number
  capacity = null
  # carrier - (optional) is a type of string
  carrier = null
  # iccid - (optional) is a type of string
  iccid = null
  # modem_id - (optional) is a type of string
  modem_id = null
  # monthly_fee - (optional) is a type of number
  monthly_fee = null
  # name - (optional) is a type of string
  name = null
  # overage - (optional) is a type of string
  overage = null
  # password - (optional) is a type of string
  password = null
  # pdn - (optional) is a type of string
  pdn = null
  # preferred_subnet - (optional) is a type of number
  preferred_subnet = null
  # private_network - (optional) is a type of string
  private_network = null
  # signal_period - (optional) is a type of number
  signal_period = null
  # signal_threshold - (optional) is a type of number
  signal_threshold = null
  # slot - (optional) is a type of string
  slot = null
  # type - (optional) is a type of string
  type = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "apn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "auth_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "billing_date" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "capacity" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "carrier" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "iccid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "modem_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "monthly_fee" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "overage" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pdn" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "preferred_subnet" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "private_network" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "signal_period" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "signal_threshold" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "slot" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "username" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "fortios_extendercontroller_dataplan" "this" {
  # apn - (optional) is a type of string
  apn = var.apn
  # auth_type - (optional) is a type of string
  auth_type = var.auth_type
  # billing_date - (optional) is a type of number
  billing_date = var.billing_date
  # capacity - (optional) is a type of number
  capacity = var.capacity
  # carrier - (optional) is a type of string
  carrier = var.carrier
  # iccid - (optional) is a type of string
  iccid = var.iccid
  # modem_id - (optional) is a type of string
  modem_id = var.modem_id
  # monthly_fee - (optional) is a type of number
  monthly_fee = var.monthly_fee
  # name - (optional) is a type of string
  name = var.name
  # overage - (optional) is a type of string
  overage = var.overage
  # password - (optional) is a type of string
  password = var.password
  # pdn - (optional) is a type of string
  pdn = var.pdn
  # preferred_subnet - (optional) is a type of number
  preferred_subnet = var.preferred_subnet
  # private_network - (optional) is a type of string
  private_network = var.private_network
  # signal_period - (optional) is a type of number
  signal_period = var.signal_period
  # signal_threshold - (optional) is a type of number
  signal_threshold = var.signal_threshold
  # slot - (optional) is a type of string
  slot = var.slot
  # type - (optional) is a type of string
  type = var.type
  # username - (optional) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "apn" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.apn
}

output "auth_type" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.auth_type
}

output "billing_date" {
  description = "returns a number"
  value       = fortios_extendercontroller_dataplan.this.billing_date
}

output "capacity" {
  description = "returns a number"
  value       = fortios_extendercontroller_dataplan.this.capacity
}

output "carrier" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.carrier
}

output "iccid" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.iccid
}

output "id" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.id
}

output "modem_id" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.modem_id
}

output "monthly_fee" {
  description = "returns a number"
  value       = fortios_extendercontroller_dataplan.this.monthly_fee
}

output "name" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.name
}

output "overage" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.overage
}

output "pdn" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.pdn
}

output "preferred_subnet" {
  description = "returns a number"
  value       = fortios_extendercontroller_dataplan.this.preferred_subnet
}

output "private_network" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.private_network
}

output "signal_period" {
  description = "returns a number"
  value       = fortios_extendercontroller_dataplan.this.signal_period
}

output "signal_threshold" {
  description = "returns a number"
  value       = fortios_extendercontroller_dataplan.this.signal_threshold
}

output "slot" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.slot
}

output "type" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.type
}

output "username" {
  description = "returns a string"
  value       = fortios_extendercontroller_dataplan.this.username
}

output "this" {
  value = fortios_extendercontroller_dataplan.this
}
```

[top](#index)