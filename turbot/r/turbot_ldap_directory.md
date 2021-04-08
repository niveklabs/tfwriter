# turbot_ldap_directory

[back](../turbot.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Resource](#resource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    turbot = ">= 1.8.2"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "turbot_ldap_directory" {
  source = "./modules/turbot/r/turbot_ldap_directory"

  # base - (required) is a type of string
  base = null
  # connectivity_test_filter - (optional) is a type of string
  connectivity_test_filter = null
  # description - (optional) is a type of string
  description = null
  # disabled_group_filter - (optional) is a type of string
  disabled_group_filter = null
  # disabled_user_filter - (optional) is a type of string
  disabled_user_filter = null
  # distinguished_name - (required) is a type of string
  distinguished_name = null
  # group_member_of_attribute - (optional) is a type of string
  group_member_of_attribute = null
  # group_membership_attribute - (optional) is a type of string
  group_membership_attribute = null
  # group_object_filter - (optional) is a type of string
  group_object_filter = null
  # group_profile_id_template - (optional) is a type of string
  group_profile_id_template = null
  # group_search_filter - (optional) is a type of string
  group_search_filter = null
  # group_sync_filter - (optional) is a type of string
  group_sync_filter = null
  # parent - (required) is a type of string
  parent = null
  # password - (required) is a type of string
  password = null
  # profile_id_template - (required) is a type of string
  profile_id_template = null
  # reject_unauthorized - (required) is a type of bool
  reject_unauthorized = null
  # tags - (optional) is a type of map of string
  tags = {}
  # title - (required) is a type of string
  title = null
  # tls_enabled - (required) is a type of bool
  tls_enabled = null
  # tls_server_certificate - (optional) is a type of string
  tls_server_certificate = null
  # url - (required) is a type of string
  url = null
  # user_canonical_name_attribute - (optional) is a type of string
  user_canonical_name_attribute = null
  # user_display_name_attribute - (optional) is a type of string
  user_display_name_attribute = null
  # user_email_attribute - (optional) is a type of string
  user_email_attribute = null
  # user_family_name_attribute - (optional) is a type of string
  user_family_name_attribute = null
  # user_given_name_attribute - (optional) is a type of string
  user_given_name_attribute = null
  # user_match_filter - (optional) is a type of string
  user_match_filter = null
  # user_object_filter - (optional) is a type of string
  user_object_filter = null
  # user_search_attributes - (optional) is a type of list of string
  user_search_attributes = []
  # user_search_filter - (optional) is a type of string
  user_search_filter = null
}
```

[top](#index)

### Variables

```terraform
variable "base" {
  description = "(required)"
  type        = string
}

variable "connectivity_test_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disabled_group_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "disabled_user_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "distinguished_name" {
  description = "(required)"
  type        = string
}

variable "group_member_of_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_membership_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_object_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_profile_id_template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_search_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_sync_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent" {
  description = "(required)"
  type        = string
}

variable "password" {
  description = "(required)"
  type        = string
}

variable "profile_id_template" {
  description = "(required)"
  type        = string
}

variable "reject_unauthorized" {
  description = "(required)"
  type        = bool
}

variable "tags" {
  description = "(optional)"
  type        = map(string)
  default     = null
}

variable "title" {
  description = "(required)"
  type        = string
}

variable "tls_enabled" {
  description = "(required)"
  type        = bool
}

variable "tls_server_certificate" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "url" {
  description = "(required)"
  type        = string
}

variable "user_canonical_name_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_display_name_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_email_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_family_name_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_given_name_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_match_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_object_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "user_search_attributes" {
  description = "(optional)"
  type        = list(string)
  default     = null
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
resource "turbot_ldap_directory" "this" {
  # base - (required) is a type of string
  base = var.base
  # connectivity_test_filter - (optional) is a type of string
  connectivity_test_filter = var.connectivity_test_filter
  # description - (optional) is a type of string
  description = var.description
  # disabled_group_filter - (optional) is a type of string
  disabled_group_filter = var.disabled_group_filter
  # disabled_user_filter - (optional) is a type of string
  disabled_user_filter = var.disabled_user_filter
  # distinguished_name - (required) is a type of string
  distinguished_name = var.distinguished_name
  # group_member_of_attribute - (optional) is a type of string
  group_member_of_attribute = var.group_member_of_attribute
  # group_membership_attribute - (optional) is a type of string
  group_membership_attribute = var.group_membership_attribute
  # group_object_filter - (optional) is a type of string
  group_object_filter = var.group_object_filter
  # group_profile_id_template - (optional) is a type of string
  group_profile_id_template = var.group_profile_id_template
  # group_search_filter - (optional) is a type of string
  group_search_filter = var.group_search_filter
  # group_sync_filter - (optional) is a type of string
  group_sync_filter = var.group_sync_filter
  # parent - (required) is a type of string
  parent = var.parent
  # password - (required) is a type of string
  password = var.password
  # profile_id_template - (required) is a type of string
  profile_id_template = var.profile_id_template
  # reject_unauthorized - (required) is a type of bool
  reject_unauthorized = var.reject_unauthorized
  # tags - (optional) is a type of map of string
  tags = var.tags
  # title - (required) is a type of string
  title = var.title
  # tls_enabled - (required) is a type of bool
  tls_enabled = var.tls_enabled
  # tls_server_certificate - (optional) is a type of string
  tls_server_certificate = var.tls_server_certificate
  # url - (required) is a type of string
  url = var.url
  # user_canonical_name_attribute - (optional) is a type of string
  user_canonical_name_attribute = var.user_canonical_name_attribute
  # user_display_name_attribute - (optional) is a type of string
  user_display_name_attribute = var.user_display_name_attribute
  # user_email_attribute - (optional) is a type of string
  user_email_attribute = var.user_email_attribute
  # user_family_name_attribute - (optional) is a type of string
  user_family_name_attribute = var.user_family_name_attribute
  # user_given_name_attribute - (optional) is a type of string
  user_given_name_attribute = var.user_given_name_attribute
  # user_match_filter - (optional) is a type of string
  user_match_filter = var.user_match_filter
  # user_object_filter - (optional) is a type of string
  user_object_filter = var.user_object_filter
  # user_search_attributes - (optional) is a type of list of string
  user_search_attributes = var.user_search_attributes
  # user_search_filter - (optional) is a type of string
  user_search_filter = var.user_search_filter
}
```

[top](#index)

### Outputs

```terraform
output "id" {
  description = "returns a string"
  value       = turbot_ldap_directory.this.id
}

output "parent_akas" {
  description = "returns a list of string"
  value       = turbot_ldap_directory.this.parent_akas
}

output "status" {
  description = "returns a string"
  value       = turbot_ldap_directory.this.status
}

output "this" {
  value = turbot_ldap_directory.this
}
```

[top](#index)