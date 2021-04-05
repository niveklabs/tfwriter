# rancher2_auth_config_activedirectory

[back](../rancher2.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    rancher2 = ">= 1.13.0"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "rancher2_auth_config_activedirectory" {
  source = "./modules/rancher2/r/rancher2_auth_config_activedirectory"

  # access_mode - (optional) is a type of string
  access_mode = null
  # allowed_principal_ids - (optional) is a type of list of string
  allowed_principal_ids = []
  # annotations - (optional) is a type of map of string
  annotations = {}
  # certificate - (optional) is a type of string
  certificate = null
  # connection_timeout - (optional) is a type of number
  connection_timeout = null
  # default_login_domain - (optional) is a type of string
  default_login_domain = null
  # enabled - (optional) is a type of bool
  enabled = null
  # group_dn_attribute - (optional) is a type of string
  group_dn_attribute = null
  # group_member_mapping_attribute - (optional) is a type of string
  group_member_mapping_attribute = null
  # group_member_user_attribute - (optional) is a type of string
  group_member_user_attribute = null
  # group_name_attribute - (optional) is a type of string
  group_name_attribute = null
  # group_object_class - (optional) is a type of string
  group_object_class = null
  # group_search_attribute - (optional) is a type of string
  group_search_attribute = null
  # group_search_base - (optional) is a type of string
  group_search_base = null
  # group_search_filter - (optional) is a type of string
  group_search_filter = null
  # labels - (optional) is a type of map of string
  labels = {}
  # nested_group_membership_enabled - (optional) is a type of bool
  nested_group_membership_enabled = null
  # port - (optional) is a type of number
  port = null
  # servers - (required) is a type of list of string
  servers = []
  # service_account_password - (required) is a type of string
  service_account_password = null
  # service_account_username - (required) is a type of string
  service_account_username = null
  # test_password - (required) is a type of string
  test_password = null
  # test_username - (required) is a type of string
  test_username = null
  # tls - (optional) is a type of bool
  tls = null
  # user_disabled_bit_mask - (optional) is a type of number
  user_disabled_bit_mask = null
  # user_enabled_attribute - (optional) is a type of string
  user_enabled_attribute = null
  # user_login_attribute - (optional) is a type of string
  user_login_attribute = null
  # user_name_attribute - (optional) is a type of string
  user_name_attribute = null
  # user_object_class - (optional) is a type of string
  user_object_class = null
  # user_search_attribute - (optional) is a type of string
  user_search_attribute = null
  # user_search_base - (required) is a type of string
  user_search_base = null
  # user_search_filter - (optional) is a type of string
  user_search_filter = null
}
```

[top](#index)

### Variables

```terraform
variable "access_mode" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "allowed_principal_ids" {
  description = "(optional)"
  type        = list(string)
  default     = null
}

variable "annotations" {
  description = "(optional) - Annotations of the resource"
  type        = map(string)
  default     = null
}

variable "certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "connection_timeout" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "default_login_domain" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "group_dn_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_member_mapping_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_member_user_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_name_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_object_class" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_search_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_search_base" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_search_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "nested_group_membership_enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "port" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "servers" {
  description = "(required)"
  type        = list(string)
}

variable "service_account_password" {
  description = "(required)"
  type        = string
}

variable "service_account_username" {
  description = "(required)"
  type        = string
}

variable "test_password" {
  description = "(required)"
  type        = string
}

variable "test_username" {
  description = "(required)"
  type        = string
}

variable "tls" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "user_disabled_bit_mask" {
  description = "(optional)"
  type        = number
  default     = null
}

variable "user_enabled_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_login_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_name_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_object_class" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_search_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_search_base" {
  description = "(required)"
  type        = string
}

variable "user_search_filter" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_auth_config_activedirectory" "this" {
  access_mode                     = var.access_mode
  allowed_principal_ids           = var.allowed_principal_ids
  annotations                     = var.annotations
  certificate                     = var.certificate
  connection_timeout              = var.connection_timeout
  default_login_domain            = var.default_login_domain
  enabled                         = var.enabled
  group_dn_attribute              = var.group_dn_attribute
  group_member_mapping_attribute  = var.group_member_mapping_attribute
  group_member_user_attribute     = var.group_member_user_attribute
  group_name_attribute            = var.group_name_attribute
  group_object_class              = var.group_object_class
  group_search_attribute          = var.group_search_attribute
  group_search_base               = var.group_search_base
  group_search_filter             = var.group_search_filter
  labels                          = var.labels
  nested_group_membership_enabled = var.nested_group_membership_enabled
  port                            = var.port
  servers                         = var.servers
  service_account_password        = var.service_account_password
  service_account_username        = var.service_account_username
  test_password                   = var.test_password
  test_username                   = var.test_username
  tls                             = var.tls
  user_disabled_bit_mask          = var.user_disabled_bit_mask
  user_enabled_attribute          = var.user_enabled_attribute
  user_login_attribute            = var.user_login_attribute
  user_name_attribute             = var.user_name_attribute
  user_object_class               = var.user_object_class
  user_search_attribute           = var.user_search_attribute
  user_search_base                = var.user_search_base
  user_search_filter              = var.user_search_filter
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_auth_config_activedirectory.this.annotations
}

output "group_dn_attribute" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.group_dn_attribute
}

output "group_member_mapping_attribute" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.group_member_mapping_attribute
}

output "group_member_user_attribute" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.group_member_user_attribute
}

output "group_name_attribute" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.group_name_attribute
}

output "group_object_class" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.group_object_class
}

output "group_search_attribute" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.group_search_attribute
}

output "group_search_base" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.group_search_base
}

output "group_search_filter" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.group_search_filter
}

output "id" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_auth_config_activedirectory.this.labels
}

output "name" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.name
}

output "nested_group_membership_enabled" {
  description = "returns a bool"
  value       = rancher2_auth_config_activedirectory.this.nested_group_membership_enabled
}

output "tls" {
  description = "returns a bool"
  value       = rancher2_auth_config_activedirectory.this.tls
}

output "type" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.type
}

output "user_enabled_attribute" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.user_enabled_attribute
}

output "user_login_attribute" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.user_login_attribute
}

output "user_name_attribute" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.user_name_attribute
}

output "user_object_class" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.user_object_class
}

output "user_search_attribute" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.user_search_attribute
}

output "user_search_filter" {
  description = "returns a string"
  value       = rancher2_auth_config_activedirectory.this.user_search_filter
}

output "this" {
  value = rancher2_auth_config_activedirectory.this
}
```

[top](#index)