# turbot_google_directory

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
module "turbot_google_directory" {
  source = "./modules/turbot/r/turbot_google_directory"

  # client_id - (required) is a type of string
  client_id = null
  # client_secret - (required) is a type of string
  client_secret = null
  # description - (optional) is a type of string
  description = null
  # group_id_template - (optional) is a type of string
  group_id_template = null
  # hosted_name - (optional) is a type of string
  hosted_name = null
  # login_name_template - (optional) is a type of string
  login_name_template = null
  # parent - (required) is a type of string
  parent = null
  # pgp_key - (optional) is a type of string
  pgp_key = null
  # pool_id - (optional) is a type of string
  pool_id = null
  # profile_id_template - (required) is a type of string
  profile_id_template = null
  # tags - (optional) is a type of map of string
  tags = {}
  # title - (required) is a type of string
  title = null
}
```

[top](#index)

### Variables

```terraform
variable "client_id" {
  description = "(required)"
  type        = string
}

variable "client_secret" {
  description = "(required)"
  type        = string
}

variable "description" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "group_id_template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "hosted_name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "login_name_template" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "parent" {
  description = "(required)"
  type        = string
}

variable "pgp_key" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "pool_id" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "profile_id_template" {
  description = "(required)"
  type        = string
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
resource "turbot_google_directory" "this" {
  # client_id - (required) is a type of string
  client_id = var.client_id
  # client_secret - (required) is a type of string
  client_secret = var.client_secret
  # description - (optional) is a type of string
  description = var.description
  # group_id_template - (optional) is a type of string
  group_id_template = var.group_id_template
  # hosted_name - (optional) is a type of string
  hosted_name = var.hosted_name
  # login_name_template - (optional) is a type of string
  login_name_template = var.login_name_template
  # parent - (required) is a type of string
  parent = var.parent
  # pgp_key - (optional) is a type of string
  pgp_key = var.pgp_key
  # pool_id - (optional) is a type of string
  pool_id = var.pool_id
  # profile_id_template - (required) is a type of string
  profile_id_template = var.profile_id_template
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
  value       = turbot_google_directory.this.directory_type
}

output "id" {
  description = "returns a string"
  value       = turbot_google_directory.this.id
}

output "key_fingerprint" {
  description = "returns a string"
  value       = turbot_google_directory.this.key_fingerprint
}

output "parent_akas" {
  description = "returns a list of string"
  value       = turbot_google_directory.this.parent_akas
}

output "status" {
  description = "returns a string"
  value       = turbot_google_directory.this.status
}

output "this" {
  value = turbot_google_directory.this
}
```

[top](#index)