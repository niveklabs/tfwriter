# fortios_user_ldap

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
module "fortios_user_ldap" {
  source = "./modules/fortios/r/fortios_user_ldap"

  # account_key_filter - (optional) is a type of string
  account_key_filter = null
  # account_key_processing - (optional) is a type of string
  account_key_processing = null
  # ca_cert - (optional) is a type of string
  ca_cert = null
  # cnid - (optional) is a type of string
  cnid = null
  # dn - (required) is a type of string
  dn = null
  # group_filter - (optional) is a type of string
  group_filter = null
  # group_member_check - (optional) is a type of string
  group_member_check = null
  # group_object_filter - (optional) is a type of string
  group_object_filter = null
  # group_search_base - (optional) is a type of string
  group_search_base = null
  # interface - (optional) is a type of string
  interface = null
  # interface_select_method - (optional) is a type of string
  interface_select_method = null
  # member_attr - (optional) is a type of string
  member_attr = null
  # name - (optional) is a type of string
  name = null
  # obtain_user_info - (optional) is a type of string
  obtain_user_info = null
  # password - (optional) is a type of string
  password = null
  # password_expiry_warning - (optional) is a type of string
  password_expiry_warning = null
  # password_renewal - (optional) is a type of string
  password_renewal = null
  # port - (optional) is a type of number
  port = null
  # search_type - (optional) is a type of string
  search_type = null
  # secondary_server - (optional) is a type of string
  secondary_server = null
  # secure - (optional) is a type of string
  secure = null
  # server - (required) is a type of string
  server = null
  # server_identity_check - (optional) is a type of string
  server_identity_check = null
  # source_ip - (optional) is a type of string
  source_ip = null
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = null
  # tertiary_server - (optional) is a type of string
  tertiary_server = null
  # two_factor - (optional) is a type of string
  two_factor = null
  # two_factor_authentication - (optional) is a type of string
  two_factor_authentication = null
  # two_factor_notification - (optional) is a type of string
  two_factor_notification = null
  # type - (optional) is a type of string
  type = null
  # user_info_exchange_server - (optional) is a type of string
  user_info_exchange_server = null
  # username - (optional) is a type of string
  username = null
}
```

[top](#index)

### Variables

```terraform
variable "account_key_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "account_key_processing" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ca_cert" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "cnid" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "dn" {
  description = "(required)"
  type        = string
}

variable "group_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_member_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_object_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_search_base" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "interface_select_method" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "member_attr" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "obtain_user_info" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password_expiry_warning" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "password_renewal" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "search_type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secondary_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "secure" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "server" {
  description = "(required)"
  type        = string
}

variable "server_identity_check" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "source_ip" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "ssl_min_proto_version" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tertiary_server" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "two_factor" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "two_factor_authentication" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "two_factor_notification" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "type" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_info_exchange_server" {
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
resource "fortios_user_ldap" "this" {
  # account_key_filter - (optional) is a type of string
  account_key_filter = var.account_key_filter
  # account_key_processing - (optional) is a type of string
  account_key_processing = var.account_key_processing
  # ca_cert - (optional) is a type of string
  ca_cert = var.ca_cert
  # cnid - (optional) is a type of string
  cnid = var.cnid
  # dn - (required) is a type of string
  dn = var.dn
  # group_filter - (optional) is a type of string
  group_filter = var.group_filter
  # group_member_check - (optional) is a type of string
  group_member_check = var.group_member_check
  # group_object_filter - (optional) is a type of string
  group_object_filter = var.group_object_filter
  # group_search_base - (optional) is a type of string
  group_search_base = var.group_search_base
  # interface - (optional) is a type of string
  interface = var.interface
  # interface_select_method - (optional) is a type of string
  interface_select_method = var.interface_select_method
  # member_attr - (optional) is a type of string
  member_attr = var.member_attr
  # name - (optional) is a type of string
  name = var.name
  # obtain_user_info - (optional) is a type of string
  obtain_user_info = var.obtain_user_info
  # password - (optional) is a type of string
  password = var.password
  # password_expiry_warning - (optional) is a type of string
  password_expiry_warning = var.password_expiry_warning
  # password_renewal - (optional) is a type of string
  password_renewal = var.password_renewal
  # port - (optional) is a type of number
  port = var.port
  # search_type - (optional) is a type of string
  search_type = var.search_type
  # secondary_server - (optional) is a type of string
  secondary_server = var.secondary_server
  # secure - (optional) is a type of string
  secure = var.secure
  # server - (required) is a type of string
  server = var.server
  # server_identity_check - (optional) is a type of string
  server_identity_check = var.server_identity_check
  # source_ip - (optional) is a type of string
  source_ip = var.source_ip
  # ssl_min_proto_version - (optional) is a type of string
  ssl_min_proto_version = var.ssl_min_proto_version
  # tertiary_server - (optional) is a type of string
  tertiary_server = var.tertiary_server
  # two_factor - (optional) is a type of string
  two_factor = var.two_factor
  # two_factor_authentication - (optional) is a type of string
  two_factor_authentication = var.two_factor_authentication
  # two_factor_notification - (optional) is a type of string
  two_factor_notification = var.two_factor_notification
  # type - (optional) is a type of string
  type = var.type
  # user_info_exchange_server - (optional) is a type of string
  user_info_exchange_server = var.user_info_exchange_server
  # username - (optional) is a type of string
  username = var.username
}
```

[top](#index)

### Outputs

```terraform
output "account_key_filter" {
  description = "returns a string"
  value       = fortios_user_ldap.this.account_key_filter
}

output "account_key_processing" {
  description = "returns a string"
  value       = fortios_user_ldap.this.account_key_processing
}

output "ca_cert" {
  description = "returns a string"
  value       = fortios_user_ldap.this.ca_cert
}

output "cnid" {
  description = "returns a string"
  value       = fortios_user_ldap.this.cnid
}

output "group_filter" {
  description = "returns a string"
  value       = fortios_user_ldap.this.group_filter
}

output "group_member_check" {
  description = "returns a string"
  value       = fortios_user_ldap.this.group_member_check
}

output "group_object_filter" {
  description = "returns a string"
  value       = fortios_user_ldap.this.group_object_filter
}

output "group_search_base" {
  description = "returns a string"
  value       = fortios_user_ldap.this.group_search_base
}

output "id" {
  description = "returns a string"
  value       = fortios_user_ldap.this.id
}

output "interface" {
  description = "returns a string"
  value       = fortios_user_ldap.this.interface
}

output "interface_select_method" {
  description = "returns a string"
  value       = fortios_user_ldap.this.interface_select_method
}

output "member_attr" {
  description = "returns a string"
  value       = fortios_user_ldap.this.member_attr
}

output "name" {
  description = "returns a string"
  value       = fortios_user_ldap.this.name
}

output "obtain_user_info" {
  description = "returns a string"
  value       = fortios_user_ldap.this.obtain_user_info
}

output "password_expiry_warning" {
  description = "returns a string"
  value       = fortios_user_ldap.this.password_expiry_warning
}

output "password_renewal" {
  description = "returns a string"
  value       = fortios_user_ldap.this.password_renewal
}

output "port" {
  description = "returns a number"
  value       = fortios_user_ldap.this.port
}

output "search_type" {
  description = "returns a string"
  value       = fortios_user_ldap.this.search_type
}

output "secondary_server" {
  description = "returns a string"
  value       = fortios_user_ldap.this.secondary_server
}

output "secure" {
  description = "returns a string"
  value       = fortios_user_ldap.this.secure
}

output "server_identity_check" {
  description = "returns a string"
  value       = fortios_user_ldap.this.server_identity_check
}

output "source_ip" {
  description = "returns a string"
  value       = fortios_user_ldap.this.source_ip
}

output "ssl_min_proto_version" {
  description = "returns a string"
  value       = fortios_user_ldap.this.ssl_min_proto_version
}

output "tertiary_server" {
  description = "returns a string"
  value       = fortios_user_ldap.this.tertiary_server
}

output "two_factor" {
  description = "returns a string"
  value       = fortios_user_ldap.this.two_factor
}

output "two_factor_authentication" {
  description = "returns a string"
  value       = fortios_user_ldap.this.two_factor_authentication
}

output "two_factor_notification" {
  description = "returns a string"
  value       = fortios_user_ldap.this.two_factor_notification
}

output "type" {
  description = "returns a string"
  value       = fortios_user_ldap.this.type
}

output "user_info_exchange_server" {
  description = "returns a string"
  value       = fortios_user_ldap.this.user_info_exchange_server
}

output "username" {
  description = "returns a string"
  value       = fortios_user_ldap.this.username
}

output "this" {
  value = fortios_user_ldap.this
}
```

[top](#index)