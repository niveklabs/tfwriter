# avi_authprofile

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
module "avi_authprofile" {
  source = "./modules/avi/d/avi_authprofile"

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
data "avi_authprofile" "this" {
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
output "description" {
  description = "returns a string"
  value       = data.avi_authprofile.this.description
}

output "http" {
  description = "returns a set of object"
  value       = data.avi_authprofile.this.http
}

output "id" {
  description = "returns a string"
  value       = data.avi_authprofile.this.id
}

output "ldap" {
  description = "returns a set of object"
  value       = data.avi_authprofile.this.ldap
}

output "name" {
  description = "returns a string"
  value       = data.avi_authprofile.this.name
}

output "pa_agent_ref" {
  description = "returns a string"
  value       = data.avi_authprofile.this.pa_agent_ref
}

output "saml" {
  description = "returns a set of object"
  value       = data.avi_authprofile.this.saml
}

output "tacacs_plus" {
  description = "returns a set of object"
  value       = data.avi_authprofile.this.tacacs_plus
}

output "tenant_ref" {
  description = "returns a string"
  value       = data.avi_authprofile.this.tenant_ref
}

output "type" {
  description = "returns a string"
  value       = data.avi_authprofile.this.type
}

output "uuid" {
  description = "returns a string"
  value       = data.avi_authprofile.this.uuid
}

output "this" {
  value = avi_authprofile.this
}
```

[top](#index)