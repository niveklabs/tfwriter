# bigip_common_license_manage_bigiq

[back](../bigip.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    bigip = ">= 1.7.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "bigip_common_license_manage_bigiq" {
  source = "./modules/bigip/r/bigip_common_license_manage_bigiq"

  # assignment_type - (required) is a type of string
  assignment_type = null
  # bigiq_address - (required) is a type of string
  bigiq_address = null
  # bigiq_login_ref - (optional) is a type of string
  bigiq_login_ref = null
  # bigiq_password - (required) is a type of string
  bigiq_password = null
  # bigiq_port - (optional) is a type of string
  bigiq_port = null
  # bigiq_token_auth - (optional) is a type of bool
  bigiq_token_auth = null
  # bigiq_user - (required) is a type of string
  bigiq_user = null
  # device_license_status - (optional) is a type of string
  device_license_status = null
  # hypervisor - (optional) is a type of string
  hypervisor = null
  # key - (optional) is a type of string
  key = null
  # license_poolname - (required) is a type of string
  license_poolname = null
  # mac_address - (optional) is a type of string
  mac_address = null
  # skukeyword1 - (optional) is a type of string
  skukeyword1 = null
  # skukeyword2 - (optional) is a type of string
  skukeyword2 = null
  # tenant - (optional) is a type of string
  tenant = null
  # unit_of_measure - (optional) is a type of string
  unit_of_measure = null
}
```

[top](#index)

### Variables

```terraform
variable "assignment_type" {
  description = "(required) - Whether the specified device is a managed/un-managed/un-reachable device "
  type        = string
}

variable "bigiq_address" {
  description = "(required) - The registration key pool to use"
  type        = string
}

variable "bigiq_login_ref" {
  description = "(optional) - Login reference for token authentication (see BIG-IQ REST docs for details)"
  type        = string
  default     = null
}

variable "bigiq_password" {
  description = "(required) - The registration key pool to use"
  type        = string
}

variable "bigiq_port" {
  description = "(optional) - The registration key pool to use"
  type        = string
  default     = null
}

variable "bigiq_token_auth" {
  description = "(optional) - Enable to use an external authentication source (LDAP, TACACS, etc)"
  type        = bool
  default     = null
}

variable "bigiq_user" {
  description = "(required) - The registration key pool to use"
  type        = string
}

variable "device_license_status" {
  description = "(optional) - Status of Licence Assignment"
  type        = string
  default     = null
}

variable "hypervisor" {
  description = "(optional) - Aws/Azure"
  type        = string
  default     = null
}

variable "key" {
  description = "(optional) - The registration key that you want to assign from the pool"
  type        = string
  default     = null
}

variable "license_poolname" {
  description = "(required) - The registration key pool to use"
  type        = string
}

variable "mac_address" {
  description = "(optional) - Sets the rate at which this license usage is billed"
  type        = string
  default     = null
}

variable "skukeyword1" {
  description = "(optional) - Sets the rate at which this license usage is billed"
  type        = string
  default     = null
}

variable "skukeyword2" {
  description = "(optional) - Sets the rate at which this license usage is billed"
  type        = string
  default     = null
}

variable "tenant" {
  description = "(optional) - optional description for the assignment in this field"
  type        = string
  default     = null
}

variable "unit_of_measure" {
  description = "(optional) - Sets the rate at which this license usage is billed"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "bigip_common_license_manage_bigiq" "this" {
  assignment_type       = var.assignment_type
  bigiq_address         = var.bigiq_address
  bigiq_login_ref       = var.bigiq_login_ref
  bigiq_password        = var.bigiq_password
  bigiq_port            = var.bigiq_port
  bigiq_token_auth      = var.bigiq_token_auth
  bigiq_user            = var.bigiq_user
  device_license_status = var.device_license_status
  hypervisor            = var.hypervisor
  key                   = var.key
  license_poolname      = var.license_poolname
  mac_address           = var.mac_address
  skukeyword1           = var.skukeyword1
  skukeyword2           = var.skukeyword2
  tenant                = var.tenant
  unit_of_measure       = var.unit_of_measure
}
```

[top](#index)

### Outputs

```terraform
output "device_license_status" {
  description = "returns a string"
  value       = bigip_common_license_manage_bigiq.this.device_license_status
}

output "id" {
  description = "returns a string"
  value       = bigip_common_license_manage_bigiq.this.id
}

output "this" {
  value = bigip_common_license_manage_bigiq.this
}
```

[top](#index)