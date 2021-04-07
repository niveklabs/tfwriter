# avi_networksecuritypolicy

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
module "avi_networksecuritypolicy" {
  source = "./modules/avi/d/avi_networksecuritypolicy"

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
data "avi_networksecuritypolicy" "this" {
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
  value       = data.avi_networksecuritypolicy.this.cloud_config_cksum
}

output "created_by" {
  description = "returns a string"
  value       = data.avi_networksecuritypolicy.this.created_by
}

output "description" {
  description = "returns a string"
  value       = data.avi_networksecuritypolicy.this.description
}

output "id" {
  description = "returns a string"
  value       = data.avi_networksecuritypolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_networksecuritypolicy.this.name
}

output "rules" {
  description = "returns a list of object"
  value       = data.avi_networksecuritypolicy.this.rules
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_networksecuritypolicy.this.tenant_ref
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_networksecuritypolicy.this.uuid
}

output "this" {
  value = avi_networksecuritypolicy.this
}
```

[top](#index)