# avi_ssopolicy

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
module "avi_ssopolicy" {
  source = "./modules/avi/d/avi_ssopolicy"

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
data "avi_ssopolicy" "this" {
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
output "authentication_policy" {
  description = "returns a set of object"
  value       = data.avi_ssopolicy.this.authentication_policy
}

output "authorization_policy" {
  description = "returns a set of object"
  value       = data.avi_ssopolicy.this.authorization_policy
}

output "id" {
  description = "returns a string"
  value       = data.avi_ssopolicy.this.id
}

output "name" {
  description = "returns a string"
  value       = data.avi_ssopolicy.this.name
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_ssopolicy.this.tenant_ref
}

output "type" {
  description = "returns a string"
  value       = data.avi_ssopolicy.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_ssopolicy.this.uuid
}

output "this" {
  value = avi_ssopolicy.this
}
```

[top](#index)