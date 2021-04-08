# turbot_saml_directory

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
module "turbot_saml_directory" {
  source = "./modules/turbot/r/turbot_saml_directory"

  # allow_group_syncing - (optional) is a type of bool
  allow_group_syncing = null
  # allow_idp_initiated_sso - (optional) is a type of bool
  allow_idp_initiated_sso = null
  # certificate - (required) is a type of string
  certificate = null
  # description - (optional) is a type of string
  description = null
  # entry_point - (required) is a type of string
  entry_point = null
  # group_filter - (optional) is a type of string
  group_filter = null
  # group_id_template - (optional) is a type of string
  group_id_template = null
  # issuer - (optional) is a type of string
  issuer = null
  # name_id_format - (optional) is a type of string
  name_id_format = null
  # parent - (required) is a type of string
  parent = null
  # pool_id - (optional) is a type of string
  pool_id = null
  # profile_groups_attribute - (optional) is a type of string
  profile_groups_attribute = null
  # profile_id_template - (required) is a type of string
  profile_id_template = null
  # sign_requests - (optional) is a type of string
  sign_requests = null
  # signature_algorithm - (optional) is a type of string
  signature_algorithm = null
  # signature_private_key - (optional) is a type of string
  signature_private_key = null
  # tags - (optional) is a type of map of string
  tags = {}
  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```terraform
variable "allow_group_syncing" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "allow_idp_initiated_sso" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "certificate" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "entry_point" {
  description = "(required)"
  type        = string
}

variable "group_filter" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id_template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "issuer" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "name_id_format" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent" {
  description = "(required)"
  type        = string
}

variable "pool_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_groups_attribute" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_id_template" {
  description = "(required)"
  type        = string
}

variable "sign_requests" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "signature_algorithm" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "signature_private_key" {
  description = "(optional)"
  type        = string
  default     = null
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
```

[top](#index)

### Resource

```terraform
resource "turbot_saml_directory" "this" {
  # allow_group_syncing - (optional) is a type of bool
  allow_group_syncing = var.allow_group_syncing
  # allow_idp_initiated_sso - (optional) is a type of bool
  allow_idp_initiated_sso = var.allow_idp_initiated_sso
  # certificate - (required) is a type of string
  certificate = var.certificate
  # description - (optional) is a type of string
  description = var.description
  # entry_point - (required) is a type of string
  entry_point = var.entry_point
  # group_filter - (optional) is a type of string
  group_filter = var.group_filter
  # group_id_template - (optional) is a type of string
  group_id_template = var.group_id_template
  # issuer - (optional) is a type of string
  issuer = var.issuer
  # name_id_format - (optional) is a type of string
  name_id_format = var.name_id_format
  # parent - (required) is a type of string
  parent = var.parent
  # pool_id - (optional) is a type of string
  pool_id = var.pool_id
  # profile_groups_attribute - (optional) is a type of string
  profile_groups_attribute = var.profile_groups_attribute
  # profile_id_template - (required) is a type of string
  profile_id_template = var.profile_id_template
  # sign_requests - (optional) is a type of string
  sign_requests = var.sign_requests
  # signature_algorithm - (optional) is a type of string
  signature_algorithm = var.signature_algorithm
  # signature_private_key - (optional) is a type of string
  signature_private_key = var.signature_private_key
  # tags - (optional) is a type of map of string
  tags = var.tags
  # title - (required) is a type of string
  title = var.title
}
```

[top](#index)

### Outputs

```terraform
output "directory_type" {
  description = "returns a string"
  value       = turbot_saml_directory.this.directory_type
}

output "id" {
  description = "returns a string"
  value       = turbot_saml_directory.this.id
}

output "parent_akas" {
  description = "returns a list of string"
  value       = turbot_saml_directory.this.parent_akas
}

output "status" {
  description = "returns a string"
  value       = turbot_saml_directory.this.status
}

output "this" {
  value = turbot_saml_directory.this
}
```

[top](#index)