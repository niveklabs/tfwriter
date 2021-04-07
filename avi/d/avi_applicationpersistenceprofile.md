# avi_applicationpersistenceprofile

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
module "avi_applicationpersistenceprofile" {
  source = "./modules/avi/d/avi_applicationpersistenceprofile"

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
data "avi_applicationpersistenceprofile" "this" {
  # name - (optional) is a type of string
  name = var.name
  # tenant_ref - (optional) is a type of string
  tenant_ref = var.tenant_ref
  # uuid - (optional) is a type of string
  uuid = var.uuid
}
```

[top](#index)

### Outputs

```terraform
output "app_cookie_persistence_profile" {
  description = "returns a set of object"
  value       = data.avi_applicationpersistenceprofile.this.app_cookie_persistence_profile
}

output "description" {
  description = "returns a string"
  value       = data.avi_applicationpersistenceprofile.this.description
}

output "hdr_persistence_profile" {
  description = "returns a set of object"
  value       = data.avi_applicationpersistenceprofile.this.hdr_persistence_profile
}

output "http_cookie_persistence_profile" {
  description = "returns a set of object"
  value       = data.avi_applicationpersistenceprofile.this.http_cookie_persistence_profile
}

output "id" {
  description = "returns a string"
  value       = data.avi_applicationpersistenceprofile.this.id
}

output "ip_persistence_profile" {
  description = "returns a set of object"
  value       = data.avi_applicationpersistenceprofile.this.ip_persistence_profile
}

output "is_federated" {
  description = "returns a bool"
  value       = data.avi_applicationpersistenceprofile.this.is_federated
}

output "name" {
  description = "returns a string"
  value       = data.avi_applicationpersistenceprofile.this.name
}

output "persistence_type" {
  description = "returns a string"
  value       = data.avi_applicationpersistenceprofile.this.persistence_type
}

output "server_hm_down_recovery" {
  description = "returns a string"
  value       = data.avi_applicationpersistenceprofile.this.server_hm_down_recovery
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_applicationpersistenceprofile.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_applicationpersistenceprofile.this.uuid
}

output "this" {
  value = avi_applicationpersistenceprofile.this
}
```

[top](#index)