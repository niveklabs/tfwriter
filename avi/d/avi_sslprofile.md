# avi_sslprofile

[back](../avi.md)

### Index

- [Example Usage](#example-usage)
- [Variables](#variables)
- [Datasource](#datasource)
- [Outputs](#outputs)

### Terraform

```terraform
terraform {
  required_providers {
    avi = ">= 0.2.3"
  }
}
```

[top](#index)

### Example Usage

```terraform
module "avi_sslprofile" {
  source = "./modules/avi/d/avi_sslprofile"

  # name - (optional) is a type of string
  name = null
  # tenant_ref - (optional) is a type of string
  tenant_ref = null
  # uuid - (optional) is a type of string
  uuid = null
}
```

[top](#index)

### Variables

```terraform
variable "name" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "tenant_ref" {
  description = "(optional)"
  type        = string
  default     = null
}

variable "uuid" {
  description = "(optional)"
  type        = string
  default     = null
}
```

[top](#index)

### Datasource

```terraform
data "avi_sslprofile" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "accepted_ciphers" {
  description = "returns a string"
  value       = data.avi_sslprofile.this.accepted_ciphers
}

output "accepted_versions" {
  description = "returns a list of object"
  value       = data.avi_sslprofile.this.accepted_versions
}

output "cipher_enums" {
  description = "returns a list of string"
  value       = data.avi_sslprofile.this.cipher_enums
}

output "ciphersuites" {
  description = "returns a string"
  value       = data.avi_sslprofile.this.ciphersuites
}

output "description" {
  description = "returns a string"
  value       = data.avi_sslprofile.this.description
}

output "dhparam" {
  description = "returns a string"
  value       = data.avi_sslprofile.this.dhparam
}

output "enable_early_data" {
  description = "returns a bool"
  value       = data.avi_sslprofile.this.enable_early_data
}

output "enable_ssl_session_reuse" {
  description = "returns a bool"
  value       = data.avi_sslprofile.this.enable_ssl_session_reuse
}

output "id" {
  description = "returns a string"
  value       = data.avi_sslprofile.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_sslprofile.this.name
}

output "prefer_client_cipher_ordering" {
  description = "returns a bool"
  value       = data.avi_sslprofile.this.prefer_client_cipher_ordering
}

output "send_close_notify" {
  description = "returns a bool"
  value       = data.avi_sslprofile.this.send_close_notify
}

output "ssl_rating" {
  description = "returns a set of object"
  value       = data.avi_sslprofile.this.ssl_rating
}

output "ssl_session_timeout" {
  description = "returns a number"
  value       = data.avi_sslprofile.this.ssl_session_timeout
}

output "tags" {
  description = "returns a list of object"
  value       = data.avi_sslprofile.this.tags
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_sslprofile.this.tenant_ref
}

output "type" {
  description = "returns a string"
  value       = data.avi_sslprofile.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_sslprofile.this.uuid
}

output "this" {
  value = avi_sslprofile.this
}
```

[top](#index)