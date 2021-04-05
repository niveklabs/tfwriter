# rancher2_auth_config_ping

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
module "rancher2_auth_config_ping" {
  source = "./modules/rancher2/r/rancher2_auth_config_ping"

  # access_mode - (optional) is a type of string
  access_mode = null
  # allowed_principal_ids - (optional) is a type of list of string
  allowed_principal_ids = []
  # annotations - (optional) is a type of map of string
  annotations = {}
  # display_name_field - (required) is a type of string
  display_name_field = null
  # enabled - (optional) is a type of bool
  enabled = null
  # groups_field - (required) is a type of string
  groups_field = null
  # idp_metadata_content - (required) is a type of string
  idp_metadata_content = null
  # labels - (optional) is a type of map of string
  labels = {}
  # rancher_api_host - (required) is a type of string
  rancher_api_host = null
  # sp_cert - (required) is a type of string
  sp_cert = null
  # sp_key - (required) is a type of string
  sp_key = null
  # uid_field - (required) is a type of string
  uid_field = null
  # user_name_field - (required) is a type of string
  user_name_field = null
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

variable "display_name_field" {
  description = "(required)"
  type        = string
}

variable "enabled" {
  description = "(optional)"
  type        = bool
  default     = null
}

variable "groups_field" {
  description = "(required)"
  type        = string
}

variable "idp_metadata_content" {
  description = "(required)"
  type        = string
}

variable "labels" {
  description = "(optional) - Labels of the resource"
  type        = map(string)
  default     = null
}

variable "rancher_api_host" {
  description = "(required)"
  type        = string
}

variable "sp_cert" {
  description = "(required)"
  type        = string
}

variable "sp_key" {
  description = "(required)"
  type        = string
}

variable "uid_field" {
  description = "(required)"
  type        = string
}

variable "user_name_field" {
  description = "(required)"
  type        = string
}
```

[top](#index)

### Resource

```terraform
resource "rancher2_auth_config_ping" "this" {
  access_mode           = var.access_mode
  allowed_principal_ids = var.allowed_principal_ids
  annotations           = var.annotations
  display_name_field    = var.display_name_field
  enabled               = var.enabled
  groups_field          = var.groups_field
  idp_metadata_content  = var.idp_metadata_content
  labels                = var.labels
  rancher_api_host      = var.rancher_api_host
  sp_cert               = var.sp_cert
  sp_key                = var.sp_key
  uid_field             = var.uid_field
  user_name_field       = var.user_name_field
}
```

[top](#index)

### Outputs

```terraform
output "annotations" {
  description = "returns a map of string"
  value       = rancher2_auth_config_ping.this.annotations
}

output "id" {
  description = "returns a string"
  value       = rancher2_auth_config_ping.this.id
}

output "labels" {
  description = "returns a map of string"
  value       = rancher2_auth_config_ping.this.labels
}

output "name" {
  description = "returns a string"
  value       = rancher2_auth_config_ping.this.name
}

output "type" {
  description = "returns a string"
  value       = rancher2_auth_config_ping.this.type
}

output "this" {
  value = rancher2_auth_config_ping.this
}
```

[top](#index)