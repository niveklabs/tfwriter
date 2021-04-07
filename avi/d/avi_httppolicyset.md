# avi_httppolicyset

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
module "avi_httppolicyset" {
  source = "./modules/avi/d/avi_httppolicyset"

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
data "avi_httppolicyset" "this" {
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
output "cloud_config_cksum" {
  description = "returns a string"
  value       = data.avi_httppolicyset.this.cloud_config_cksum
}

output "created_by" {
  description = "returns a string"
  value       = data.avi_httppolicyset.this.created_by
}

output "description" {
  description = "returns a string"
  value       = data.avi_httppolicyset.this.description
}

output "http_request_policy" {
  description = "returns a set of object"
  value       = data.avi_httppolicyset.this.http_request_policy
}

output "http_response_policy" {
  description = "returns a set of object"
  value       = data.avi_httppolicyset.this.http_response_policy
}

output "http_security_policy" {
  description = "returns a set of object"
  value       = data.avi_httppolicyset.this.http_security_policy
}

output "id" {
  description = "returns a string"
  value       = data.avi_httppolicyset.this.id
}

output "is_internal_policy" {
  description = "returns a bool"
  value       = data.avi_httppolicyset.this.is_internal_policy
}

output "name" {
  description = "returns a string"
  value       = data.avi_httppolicyset.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_httppolicyset.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_httppolicyset.this.uuid
}

output "this" {
  value = avi_httppolicyset.this
}
```

[top](#index)