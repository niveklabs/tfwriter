# vcd_org_user

[back](../vcd.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    vcd = ">= 3.2.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "vcd_org_user" {
  source = "./modules/vcd/r/vcd_org_user"

  # deployed_vm_quota - (optional) is a type of number
  deployed_vm_quota = null
  # description - (optional) is a type of string
  description = null
  # email_address - (optional) is a type of string
  email_address = null
  # enabled - (optional) is a type of bool
  enabled = null
  # full_name - (optional) is a type of string
  full_name = null
  # instant_messaging - (optional) is a type of string
  instant_messaging = null
  # is_group_role - (optional) is a type of bool
  is_group_role = null
  # is_locked - (optional) is a type of bool
  is_locked = null
  # name - (required) is a type of string
  name = null
  # org - (optional) is a type of string
  org = null
  # password - (optional) is a type of string
  password = null
  # password_file - (optional) is a type of string
  password_file = null
  # provider_type - (optional) is a type of string
  provider_type = null
  # role - (required) is a type of string
  role = null
  # stored_vm_quota - (optional) is a type of number
  stored_vm_quota = null
  # take_ownership - (optional) is a type of bool
  take_ownership = null
  # telephone - (optional) is a type of string
  telephone = null
}
```

[top](#index)

### Variables

```terraform
variable "deployed_vm_quota" {
  description = "(optional) - Quota of vApps that this user can deploy. A value of 0 specifies an unlimited quota."
  type        = number
  default     = null
}

variable "description" {
  description = "(optional) - The user's description"
  type        = string
  default     = null
}

variable "email_address" {
  description = "(optional) - The user's email address"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional) - True if the user is enabled and can log in."
  type        = bool
  default     = null
}

variable "full_name" {
  description = "(optional) - The user's full name"
  type        = string
  default     = null
}

variable "instant_messaging" {
  description = "(optional) - The user's telephone"
  type        = string
  default     = null
}

variable "is_group_role" {
  description = "(optional) - True if this user has a group role."
  type        = bool
  default     = null
}

variable "is_locked" {
  description = "(optional) - If the user account has been locked due to too many invalid login attempts, the value will change to true (only the system can lock the user). To unlock the user re-set this flag to false."
  type        = bool
  default     = null
}

variable "name" {
  description = "(required) - User's name. Only lowercase letters allowed. Cannot be changed after creation"
  type        = string
}

variable "org" {
  description = "(optional) - The name of organization to use, optional if defined at provider level. Useful when connected as sysadmin working across different organizations"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional) - The user's password. This value is never returned on read. Either \"password\" or \"password_file\" must be included on creation."
  type        = string
  default     = null
}

variable "password_file" {
  description = "(optional) - Name of a file containing the user's password. Either \"password_file\" or \"password\" must be included on creation."
  type        = string
  default     = null
}

variable "provider_type" {
  description = "(optional) - Identity provider type for this this user. One of: 'INTEGRATED', 'SAML', 'OAUTH'. When empty, the default value 'INTEGRATED' is used."
  type        = string
  default     = null
}

variable "role" {
  description = "(required) - Role within the organization"
  type        = string
}

variable "stored_vm_quota" {
  description = "(optional) - Quota of vApps that this user can store. A value of 0 specifies an unlimited quota."
  type        = number
  default     = null
}

variable "take_ownership" {
  description = "(optional) - Take ownership of user's objects on deletion."
  type        = bool
  default     = null
}

variable "telephone" {
  description = "(optional) - The user's telephone"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "vcd_org_user" "this" {
  # deployed_vm_quota - (optional) is a type of number
  deployed_vm_quota = var.deployed_vm_quota
  # description - (optional) is a type of string
  description = var.description
  # email_address - (optional) is a type of string
  email_address = var.email_address
  # enabled - (optional) is a type of bool
  enabled = var.enabled
  # full_name - (optional) is a type of string
  full_name = var.full_name
  # instant_messaging - (optional) is a type of string
  instant_messaging = var.instant_messaging
  # is_group_role - (optional) is a type of bool
  is_group_role = var.is_group_role
  # is_locked - (optional) is a type of bool
  is_locked = var.is_locked
  # name - (required) is a type of string
  name = var.name
  # org - (optional) is a type of string
  org = var.org
  # password - (optional) is a type of string
  password = var.password
  # password_file - (optional) is a type of string
  password_file = var.password_file
  # provider_type - (optional) is a type of string
  provider_type = var.provider_type
  # role - (required) is a type of string
  role = var.role
  # stored_vm_quota - (optional) is a type of number
  stored_vm_quota = var.stored_vm_quota
  # take_ownership - (optional) is a type of bool
  take_ownership = var.take_ownership
  # telephone - (optional) is a type of string
  telephone = var.telephone
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = vcd_org_user.this.id
}

output "this" {
  value = vcd_org_user.this
}
```

[top](#index)