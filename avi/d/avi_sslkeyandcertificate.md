# avi_sslkeyandcertificate

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
module "avi_sslkeyandcertificate" {
  source = "./modules/avi/d/avi_sslkeyandcertificate"

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
data "avi_sslkeyandcertificate" "this" {
  name       = var.name
  tenant_ref = var.tenant_ref
  uuid       = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "ca_certs" {
  description = "returns a list of object"
  value       = data.avi_sslkeyandcertificate.this.ca_certs
}

output "certificate" {
  description = "returns a set of object"
  value       = data.avi_sslkeyandcertificate.this.certificate
}

output "certificate_base64" {
  description = "returns a bool"
  value       = data.avi_sslkeyandcertificate.this.certificate_base64
}

output "certificate_management_profile_ref" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.certificate_management_profile_ref
}

output "created_by" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.created_by
}

output "dynamic_params" {
  description = "returns a list of object"
  value       = data.avi_sslkeyandcertificate.this.dynamic_params
}

output "enckey_base64" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.enckey_base64
}

output "enckey_name" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.enckey_name
}

output "format" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.format
}

output "hardwaresecuritymodulegroup_ref" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.hardwaresecuritymodulegroup_ref
}

output "id" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.id
}

output "key" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.key
}

output "key_base64" {
  description = "returns a bool"
  value       = data.avi_sslkeyandcertificate.this.key_base64
}

output "key_params" {
  description = "returns a set of object"
  value       = data.avi_sslkeyandcertificate.this.key_params
}

output "key_passphrase" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.key_passphrase
}

output "name" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.name
}

output "status" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.status
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.tenant_ref
}

output "type" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_sslkeyandcertificate.this.uuid
}

output "this" {
  value = avi_sslkeyandcertificate.this
}
```

[top](#index)